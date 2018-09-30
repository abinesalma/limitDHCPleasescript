# limitDHCPleasescript
#Limit client otomatis pada simple queues berdasarkan dhcp lease
#buat nama parent terlebih dahulu dengan nama=GUESTS
#tentukan iprange target dan bandwidth internet
#copy dan paste script dibawah ini pada: IP-DHCP Server-Lease Script

:local queueName "Guest $leaseActMAC";

:if ($leaseBound = "1") do={
    /queue simple add name=$queueName parent=GUESTS target=($leaseActIP . "/32") limit-at=256k/1024k max-limit=1536k/10240k comment=[/ip dhcp-server lease get [find where active-mac-address=$leaseActMAC && active-address=$leaseActIP] host-name];
} else={
    /queue simple remove $queueName
}
