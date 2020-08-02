*****YAML IOSXR Inline & Offline Analysis Incident/Event Management*****

This Ansible project help to do inline analysis while an incident triggered on network level, for testing simple commands have been taken to analyze and output results are conditional which pin point alarming situation.

Offline Analysis can also doable as outputs saved in CSV file.

All needed files have been uploaded, for case base secanrio can be demonstrate on GNS3 all related files have been uploaded too.

*****Requirements*****

ansible 2.5 or later 2.7.10

GNS3

xrv-k9-5.3.1


*****Language*****

YAML


*****License*****

GPLv3


*****Steps to accomplish Inline & Offline Analysis for Event/Incident Management are below*****
- Ansible Controller installed either on Redhat (Centos) or Window
- GNS3 with IOSXRv capability, - GNS3 Topology uploaded
- Logical connectivity between Ansible controller and GNS Nodes example (IOSXRv)
- Name resolution either via DNS or via local Host file


*****Command*****
time ansible-playbook IOSXRtest.yml >>>time help to find out how quick code implemented in running environment to acquire desire results


*****Note*****
Shared code designed on basic commands but we could moderate or enhaned this code and build multiple scenarios on base of our routine case studies on networks or technologies
YML Playbook can be import in CMLv2


*****Result*****
[root@osboxes9 ansible]# time ansible-playbook IOSXRtest.yml

PLAY [XR Router Troubleshooting] **********************************************************************************************************************************************************************************

TASK [Core Troubleshooting Commands] ******************************************************************************************************************************************************************************
ok: [IOSXR_West] => (item=show clock)
ok: [IOSXR_South] => (item=show clock)
ok: [IOSXR_West] => (item=show platform)
ok: [IOSXR_South] => (item=show platform)
ok: [IOSXR_West] => (item=show redundancy)
ok: [IOSXR_South] => (item=show redundancy)
ok: [IOSXR_West] => (item=show proc cpu | ex "0%      0%       0%")
ok: [IOSXR_South] => (item=show proc cpu | ex "0%      0%       0%")
ok: [IOSXR_West] => (item=show memory sum location all | in "node|Pyhsical|available")
ok: [IOSXR_South] => (item=show memory sum location all | in "node|Pyhsical|available")
ok: [IOSXR_West] => (item=show int description | i down)
ok: [IOSXR_South] => (item=show int description | i down)
ok: [IOSXR_West] => (item=show log | i, ch)
ok: [IOSXR_South] => (item=show log | i, ch)

*****Sample of Desired Output*****
TASK [Platform Hardware Check] ************************************************************************************************************************************************************************************
skipping: [IOSXR_South]
skipping: [IOSXR_West]

TASK [Redundancy Check] *******************************************************************************************************************************************************************************************
ok: [IOSXR_West] => {
    "msg": "IOSXR_West show_redundancy indicates card is not present: "
}
ok: [IOSXR_South] => {
    "msg": "IOSXR_South show_redundancy indicates card is not present: "
}
