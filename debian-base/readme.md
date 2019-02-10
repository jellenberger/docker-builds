# jellenberger/debian-base

This is a Docker build for a simple Debian image. It is essentially the Debian slim image with a non-root user added.

The user, `appuser`, has a home directory at `\home\appuser`. `appuser` has a user and primary group ids of 1000.
