## ansible-dynamic-ec2inventory

- Set the credentials as environment variable to pass to the dyanmic inventory (ec2.py) scripts

      export AWS_ACCESS_KEY_ID='AK123'
      export AWS_SECRET_ACCESS_KEY='abc123'


 - test the script and connection with valid aws credentials, it will returns the list of ec2 instances grouped in json with tag name which can be used as host in ansible playbook

       python inventories/ec2.py --list


**NOTE:** If need to get the private IP's of ec2 instances then enable `vpc_destination_variable`
in `ec2.in` file

    vpc_destination_variable = private_ip_address


- Execute the ansible playbook to run the task on ec2-instance

      ansible-playbook -i inventories/ec2.py playbooks/sample.yml
