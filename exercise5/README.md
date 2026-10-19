# Exercise 5 --- Docker Security with AppArmor and Python

## Overview

This exercise demonstrates running a Flask application inside Docker
with a custom AppArmor profile. The profile is used to restrict selected
actions while allowing the web application to continue running.

## Objectives

-   Build a Docker image for the Flask application.
-   Apply a custom AppArmor profile to a Docker container.
-   Verify the profile assigned to the container and check AppArmor
    enforcement.
-   Test restricted file access and executable access.
-   Confirm that the Flask application remains accessible.

## Project Setup

Build the image from the `exercise5` directory:

``` bash
docker build -t flask-apparmor .
```

The image contains the Flask application and runs it inside the
container.

## 1. Build and Run the Flask Container

Run the container with the custom AppArmor profile:

``` bash
sudo docker run -d \
  --name flask-secure \
  --security-opt apparmor=my-apparmor-profile \
  -p 5001:5000 \
  flask-apparmor
```

Port `5001` on the host is mapped to port `5000` inside the container.
This avoids a conflict if another service is already using host port
`5000`.

## 2. Verify the Application and Build

The first screenshot shows the Docker image build and a successful HTTP
request to the Flask application. The application returns the expected
greeting:

``` text
Hello, this is a secure Flask application running inside a Docker container!
```

![Docker image build and successful Flask
response](ex5.1.png)

## 3. AppArmor Profile and Restriction Tests

The custom profile, `my-apparmor-profile`, includes rules intended to:

-   Allow the Python interpreter and access to the Flask application
    files.
-   Deny reading `/etc/passwd`.
-   Deny execution from `/bin` and `/usr/bin`.
-   Allow IPv4 stream networking.
-   Deny the `sys_admin` capability.

The second screenshot shows the profile rules and terminal tests.
Reading `/etc/passwd` is denied, and attempting to run `/usr/bin/which`
is denied. These results demonstrate the tested restrictions.

![AppArmor profile and restricted action
tests](ex5.2.png)

## 4. Verification Commands

Use the following commands to check the container configuration and
AppArmor enforcement:

``` bash
sudo docker inspect flask-secure --format 'AppArmor profile: {{.AppArmorProfile}}'
sudo aa-status
curl http://localhost:5001
```

The expected profile name is `my-apparmor-profile`. In `aa-status`,
verify that the Python process is listed under that profile in
**enforce** mode. The `curl` request should return the Flask greeting.

## Conclusion

The screenshots document a successful Docker image build, a responding
Flask application, the configured custom AppArmor profile, and denial of
selected restricted operations. The tests shown verify those specific
actions; they do not establish that every rule in the profile has been
tested.

## Cleanup

Remove the running test container when you are finished:

``` bash
sudo docker rm -f flask-secure
```
