Check Zeek version and if it is installed
`zeek -v`

Start Zeek as a service (control module)
`zeekctl`

*within the control module*
`status`
`start`
`stop`

## PCAP Reading Mode

`zeek -C -r sample.pcap`

| Parameter | Description                           |
| --------- | ------------------------------------- |
| -r        | reading option to process a pcap file |
| -C        | ignore checksum errors                |

