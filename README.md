# EX188 Notes
Notes and Lesson Learnt from EX188

I've taken the exam on 17th May 2023 for EX188V4. The following tips and hints may not be applicable in the future if there is any revision to the exams. This note will be left unmaintained and no future updates are expected.

## Exam Content
The following topics were not tested:
- Podman Compose
- Openshift
- Multi-stage Containerfile
- SELinux and container permission related stuff

Each task is to test on the following objective:
- Implement images using Podman
- Manage images
- Run containers locally using Podman
- Run multi-container applications with Podman
- Troubleshoot containerized applications

## Tips
There are about 5 or 6 questions to test on the above objectives, if you're confident, spend less time and quickly complete all the questions to save more time to tackle the Troubleshooting question. I took about 1.5 hours to identify the issues within that task.

Be careful when stopping and removing containers during the Troubleshooting questions. The container names are similar to the previous questions, with an append of <CONTAINER-NAME>-ts. Remember that your containers have to be persisted! Don't accidentally delete containers of the previous tasks.

There is a list of verification tasks after each question. It's not mandatory but recommended to do to verify your solution.
  
During troubleshooting, sudo commands can't be run, such as `sudo nsenter -t <PID> -n ss -pant`.
That being said, `podman exec <CONTAINER_NAME> ss -pant` will also return error.

There is no multi-stage Containerfile, but know the difference between ENV and ARG and how to use ARGs at build time. Also know that ARGs can be passed as variable in build time by executing:
`podman build -t <IMAGE_NAME:TAG> --build-arg <ARG_KEY:VALUE>`

