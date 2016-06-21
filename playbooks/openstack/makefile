##############################
controller=192.168.109.11
nove_nodes=192.168.109.11
nentron_nodes=192.168.109.11
glance_nodes=192.168.109.11
swift_nodes=192.168.109.11
cinder_nodes=192.168.109.11
manina_nodes=192.168.109.11
horizon_nodes=192.168.109.11
all_hosts=192.168.109.11
##############################

##############################
#all_hosts=`ansible all --list-hosts`
user=wchen
cmd=ansible-playbook
vars=--extra-vars "hosts=${all_hosts} user=${user}" -s -K

#################################
main: keystone

keystone:keystone.yml
	${cmd} $<  ${vars}

nova:nova.yml
	${cmd} $<  ${vars}

neutron:neutron.yml
	${cmd} $<  ${vars}
	
glance:glance.yml
	${cmd} $<  ${vars}

swift:swift.yml
	${cmd} $<  ${vars}
	
cinder:cinder.yml
	${cmd} $<  ${vars}

manina:manina.yml
	${cmd} $< ${vars}

horizon:horizon.yml
	${cmd} $<  ${vars}

prepare:prepare.yml
	${cmd} $<  ${vars}

check:
	${cmd} prepare.yml ${vars} --syntax-check 
	${cmd} keystone.yml ${vars} --syntax-check 	
	
#################################
