# Membuat simple queues auto berdasarkan dhcp lease serta membagi bandwidth secara dinamis berdasarkan jumlah koneksi

#setiap ada device yang mendapatkan ip dari dhcp server dan berstatus "bound" pada dhcp lease, akan dimunculkan pada simple queues secara otomatis

#simple queues otomatis hilang bila id device hilang dari dhcp lease

#buat nama parent terlebih dahulu dengan nama=GUESTS

#tentukan ip range target dan bandwidth internet

#copy dan paste script dibawah ini pada: IP-DHCP Server-Lease Script

#sesuaikan limit-at dan max-limit sesuai bandwidth yang kamu miliki




