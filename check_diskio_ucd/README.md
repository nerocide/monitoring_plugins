Disk IO over SNMP
=================

Source script written by hstadler downloaded from https://exchange.nagios.org/directory/Plugins/Network-Protocols/SNMP/Check-DiskIO-via-SNMP/details

New features:
	- if no selection made, retreive all device IO/s
	- device selection is regex compliant (option -d)

Features:
	- SNMP v1/2/3 compliant
	- get :
		- Read/Write IO
		- Read MB/sec
		- Write MB/sec
		- Read IO/sec
		- Write IO/sec
		- Total IO/sec

Examples:

	- Select all device matching *sda*
	./check_diskio_ucd.pl -H localhost -d sda -w 9 -c 10
	DISKIO OK - No Problems found (Write 0 MB/s)|sda_ReadMB=0.00MB/s sda_WriteMB=0.04MB/s sda_ReadIO=0.00IO/s sda_WriteIO=6.60IO/s sda_TotalIO=6.60IO/s sda1_ReadMB=0.00MB/s sda1_WriteMB=0.00MB/s sda1_ReadIO=0.00IO/s sda1_WriteIO=0.00IO/s sda1_TotalIO=0.00IO/s sda2_ReadMB=0.00MB/s sda2_WriteMB=0.03MB/s sda2_ReadIO=0.00IO/s sda2_WriteIO=5.00IO/s sda2_TotalIO=5.00IO/s sda3_ReadMB=0.00MB/s sda3_WriteMB=0.02MB/s sda3_ReadIO=0.00IO/s sda3_WriteIO=1.00IO/s sda3_TotalIO=1.00IO/s 

	- Select device sda
	./check_diskio_ucd.pl -H localhost -d "sda$" -w 9 -c 10
	DISKIO OK - No Problems found (Write 0 MB/s)|sda_ReadMB=0.00MB/s sda_WriteMB=0.01MB/s sda_ReadIO=0.00IO/s sda_WriteIO=1.60IO/s sda_TotalIO=1.60IO/s 

	- No selection, get all devices datas:
	./check_diskio_ucd.pl -H localhost -w 9 -c 10
	DISKIO OK - No Problems found (Write 0 MB/s)|sda_ReadMB=0.02MB/s sda_WriteMB=0.06MB/s sda_ReadIO=1.20IO/s sda_WriteIO=5.40IO/s sda_TotalIO=6.60IO/s sda1_ReadMB=0.00MB/s sda1_WriteMB=0.00MB/s sda1_ReadIO=0.00IO/s sda1_WriteIO=0.00IO/s sda1_TotalIO=0.00IO/s sda2_ReadMB=0.02MB/s sda2_WriteMB=0.03MB/s sda2_ReadIO=1.20IO/s sda2_WriteIO=2.00IO/s sda2_TotalIO=3.20IO/s sda3_ReadMB=0.00MB/s sda3_WriteMB=0.03MB/s sda3_ReadIO=0.00IO/s sda3_WriteIO=2.40IO/s sda3_TotalIO=2.40IO/s dm-0_ReadMB=0.00MB/s dm-0_WriteMB=0.00MB/s dm-0_ReadIO=0.00IO/s dm-0_WriteIO=1.00IO/s dm-0_TotalIO=1.00IO/s dm-1_ReadMB=0.02MB/s dm-1_WriteMB=0.01MB/s dm-1_ReadIO=1.20IO/s dm-1_WriteIO=2.00IO/s dm-1_TotalIO=3.20IO/s dm-2_ReadMB=0.00MB/s dm-2_WriteMB=0.03MB/s dm-2_ReadIO=0.00IO/s dm-2_WriteIO=2.60IO/s dm-2_TotalIO=2.60IO/s dm-3_ReadMB=0.00MB/s dm-3_WriteMB=0.00MB/s dm-3_ReadIO=0.00IO/s dm-3_WriteIO=0.00IO/s dm-3_TotalIO=0.00IO/s dm-4_ReadMB=0.00MB/s dm-4_WriteMB=0.00MB/s dm-4_ReadIO=0.00IO/s dm-4_WriteIO=0.00IO/s dm-4_TotalIO=0.00IO/s dm-5_ReadMB=0.00MB/s dm-5_WriteMB=0.00MB/s dm-5_ReadIO=0.00IO/s dm-5_WriteIO=0.80IO/s dm-5_TotalIO=0.80IO/s dm-6_ReadMB=0.00MB/s dm-6_WriteMB=0.00MB/s dm-6_ReadIO=0.00IO/s dm-6_WriteIO=0.00IO/s dm-6_TotalIO=0.00IO/s dm-7_ReadMB=0.00MB/s dm-7_WriteMB=0.00MB/s dm-7_ReadIO=0.00IO/s dm-7_WriteIO=0.00IO/s dm-7_TotalIO=0.00IO/s dm-8_ReadMB=0.00MB/s dm-8_WriteMB=0.00MB/s dm-8_ReadIO=0.00IO/s dm-8_WriteIO=0.00IO/s dm-8_TotalIO=0.00IO/s dm-9_ReadMB=0.00MB/s dm-9_WriteMB=0.00MB/s dm-9_ReadIO=0.00IO/s dm-9_WriteIO=0.00IO/s dm-9_TotalIO=0.00IO/s
