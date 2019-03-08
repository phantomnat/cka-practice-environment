FROM phantomnat/gateone:16.04

COPY conf.d/ /etc/gateone/conf.d/

RUN apt-get update --fix-missing \
	&& apt-get install wget curl vim openssh-client iputils-ping telnet nmap -y \
	&& curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.12.6/bin/linux/amd64/kubectl \
	&& chmod +x ./kubectl \
	&& mv ./kubectl /usr/local/bin/kubectl \
	# && ssh-keygen -N "" -t rsa -f ~/.ssh/id_rsa \
    # && cat ~/.ssh/id_rsa.pub > ~/.ssh/authorized_keys \
	&& apt-get clean all

CMD ["/usr/local/bin/update_and_run_gateone", "--log_file_prefix=/gateone/logs/gateone.log", "--noupdate"]
