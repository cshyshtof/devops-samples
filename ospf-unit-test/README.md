# devops-samples
Sample codes for devops demos

## ospf-unit-test

Simple ansible code for running unit tests when configuring OSPF on Cisco Nexus switches. This code was used for demo on PLNOG19 conference. The video (polish version) is available [here](https://www.youtube.com/watch?v=BwKUtVAwkvw)

1. Prepare your VIRL or any other lab environment, as depicted on the below diagram

![Diagram](diagram.png?raw=true "Diagram")

2. Run *ansible-playbook -i hosts-test deploy-config.yml* to configure Nexus switches

3. Verify OSPF
 * Run *show ip ospf neighbor* command to verify that OSPF is not working properly
 * Run *ansible-playbook -i hosts-test deploy-verify.yml* to check what is wrong with OSPF

4. Fix MTU issue in *host_vars/nx1.yml*

5. Run *ansible-playbook -i hosts-test deploy-config.yml* again

6. Verify OSPF
 * Run *show ip ospf neighbor* command to verify that OSPF is working properly
 * Run *ansible-playbook -i hosts-test deploy-verify.yml* to verify final ping test

__Prerequisites__
 - For full pipeline tests, configure Gitlab and Jenkins
