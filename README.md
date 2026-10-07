# lab-builder

Builds the services of a [MitsuruTech](https://mitsurutech.co.uk) lab from a teacher's
public GitHub repository, and publishes each image to
[`ghcr.io/mitsurutech/lab-images`](https://github.com/orgs/mitsurutech/packages/container/package/lab-images).

A lab is a set of containers described by a compose file. When a teacher publishes a commit
of a lab whose compose file says `build:`, the website starts `Build a lab image` here once
per built service. The image is tagged `<lab>-<service>-<commit>`, and the lab machines pull
it from there. No teacher's Dockerfile ever runs on a lab machine.

**What is published is public.** Only public repositories are built. Anything a Dockerfile
copies in, and any value it sets with `ENV` or `ARG`, can be read by anybody who pulls the
image: keep secrets in an `env_file`, which the site adds when a copy starts and which is
never built into the image.

Builds run on GitHub's own runners, started only by the website with a token that can do
nothing else. To report an image that should not be here, write to the address on
mitsurutech.co.uk/contact.
