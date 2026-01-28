 TShark Commands Used-

Capture traffic -
sudo tshark -i eth0 -w phishing_click.pcap

Filter HTTP traffic -
tshark -r phishing_click.pcap -Y http

Extract HTTP requests -
tshark -r phishing_click.pcap -Y http.request \
-T fields -e frame.time -e ip.src -e ip.dst -e http.request.method -e http.request.uri

Count phishing link clicks -
tshark -r phishing_click.pcap -Y 'http.request.uri contains "verify"' \
-T fields -e http.request.uri | sort | uniq -c

Conversation summary -
tshark -r phishing_click.pcap -q -z conv,ip

Detect repeated behavior (phishing pattern)
tshark -r phishing_click.pcap -Y http.request \
-T fields -e ip.src | sort | uniq -c

Show timeline of attack -
tshark -r phishing_click.pcap -Y http.request \
-T fields -e frame.time -e http.request.uri

Extract only suspicious URIs -
tshark -r phishing_click.pcap -Y 'http.request.uri contains "verify"'
