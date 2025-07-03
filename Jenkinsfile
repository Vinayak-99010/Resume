rsync -avz \
--include '*/' \
--include '*.html' \
--include '*.css' \
--exclude '*' \
-e "ssh -i /var/lib/jenkins/.ssh/webserver_key -o StrictHostKeyChecking=no" \
html/ ec2-user@54.152.169.2:/var/www/html/
