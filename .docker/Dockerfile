FROM ubuntu:latest

RUN apt-get install gnupg wget -y
RUN wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor |  tee /usr/share/keyrings/trivy.gpg > /dev/null
RUN echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb generic main" |  tee -a /etc/apt/sources.list.d/trivy.list
RUN apt-get update
RUN apt-get install trivy

WORKDIR /trivy