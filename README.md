# Project Python: Super Cashier

Dipersiapkan untuk pengerjaan Project untuk kelas Python Pacmann.

## Latar belakang masalah

Suatu supermarket besar di Indonesia membutuhkan suatu sistem kasir yang memampukan para Customer untuk melakukan self-service. Customer dapat memasukkan secara mandiri item apa yang dibeli, jumlah item yang dibeli dan harga item yang dibeli. 
Fungsi yang adanya sedianya disiapkan dengan tetap mengedepankan kemudahan bagi Customer seperti tampilan interaktif berupa pilihan dalam bentuk menu dan kemampuan untuk melakukan pemeriksaan dan koreksi terhadap daftar belanja Customer.  

## Fungsi-fungsi yang dibutuhkan

1. Customer mendapatkan suatu tampilan personal yang mudah bagi seseorang berbelanja. Dalam hal ini berupa satu tampilan daftar belanja, satu tampilan transaksi.
2. Tampilan yang intuitif cukup: Nama item, Jumlah item dan Harga per Item.
3. Customer dapat melakukan koreksi terhadap daftar belanjaan, yang memungkinkan untuk memperbaiki sesuai input yang digunakannya pada saat berbelanja di awal.
4. Customer dapat melakukan pembatalan terhadap daftar belanjaannya, baik itu pembatalan terhadap satu barang, maupun terhadap keseluruhan daftar secara sekaligus.
5. Pada saat customer sudah selesai berbelanja, sistem dapat membantu customer untuk memeriksa daftar belanjanya dan tetap sesuai dengan dengan entry awal maupun koreksi yang sudah dilakuan. 
6. Setelah memastikan daftar belanja yang sudah diperiksa, customer dapat menyelesaikan kegiatan belanja dengan mendapatkan perhitungan akhir untuk belanja yang sudah dilakukan.
7. Untuk lebih memuaskan Customer, pihak Supermarket juga sudah menyediakan sejumlah discount untuk total belanja Customer jika telah mencapai nilai-nilai tertentu dengan discount yang juga disesuaikan. Discount berupa 10% jika total belanja lebih dari Rp500.000,-, discount berupa 8% jika total belanja lebih dari Rp300.000,-, dan discount berupa 5% jika total belanja lebih dari Rp200.000,-

## Fungsi-fungsi pelengkap yang ditambahkan programmer

1. Pada sistem disediakan daftar item yang memudahkan pembeli untuk memasukkan nama barang yang sesuai dengan spesifikasi yang dimiliki Supermarket. Hal-hal informatif spesifik yang diperlukan adalah harga satuan dan unit satuan dari barang. 
2. Pada sistem disediakan tampilan tabular sederhana untuk tetap menginformasikan Customer mengenai daftar belanja yang sudah dimiliki.
3. Pada sistem disediakan kemampuan kemudahan bagi Customer yang akan melakukan modifikasi:
> - Jika customer melakukan penambahan data belanja sesuai dengan daftar stok yang ada maka perubahan nama, customer dipastikan mendapat informasi harga dan unit yang informatif.
> - Perubahan terhadap nama jenis barang, maka pada harga per unit akan langsung disesuaikan.
> - Perubahan terhadap jumlah uang yang dibayarkan, jika jumlah yang baru lebih besar daripada harga total barang, maka akan dicatat sesuai dengan harga total barang. 
> - Perubahan terhadap jumlah uang yang dibayarkan, jika kelebihannya jumlah mencapai kelipatan angka bulat dari harga, maka jumlah unit akan diberikan sesuai kelipatannya.
> - Perubahan terhadap jumlah uang yang dibayarkan, jika jumlah yang baru ternyata lebih rendah daripada harga total barang maka jumlah unit akan disesuaikan dengan total harga barang yang lebih kecil.

## Fungsi dan Atribut 

class Transaction <br>
constants:  <br>
  LOWER_AMOUNT = 200_000 <br>
  LOWER_DISCOUNT = 0.05 <br>
  MID_AMOUNT = 300_000 <br>
  MID_DISCOUNT = 0.08 <br>
  HIGH_AMOUNT = 500_000 <br>
  HIGH_DISCOUNT = 0.1 <br>

methods: <br>
getPricelist() <br>
new_basket_record(item_name, param_qty=0,param_paid=0) <br>
Description: Records builder: providing one record for each transaction entry made. This function will prepare one tuple for each transaction and return the tupple with item name, item quantity, item unit-price, item unit and item total price. <br> <br>

Parameters:  <br>
transaction_class : Class  <br> <br>
The Transaction Class object. <br>
item_name : str  <br> Nama item belanja Customer  <br>
param_qty : str  <br> Jumlah item belanja Customer  <br>
param_paid : str  <br> Harga item belanja Customer <br>

- add_item(item_name, item_qty=1, item_price=0) <br>
- update_item_name(item_name, new_item_name) <br>
- update_item_qty(item_name, new_item_qty) <br>
- update_item_price(item_name, new_item_price) <br>
- delete_item(item_name) <br>
- reset_transaction() <br>
- check_order() <br>
- total_price() <br> <br>

keterangan <br>
- item_name, new_item_name : str  <br> 
Nama item belanja Customer  <br>
- item_qty, new_item_qty : str  <br> 
Jumlah item belanja Customer  <br>
- item_price, new_item_price : str  <br> 
Harga item belanja Customer <br>

## Test Case (Hasil dalam Video)

### Test #1 (Berhasil)

Customer ingin menambahkan dua item baru menggunakan method add_item(). Item yang ditambahkan adalah sebagai berikut:
-	Nama item: Ayam Goreng, qty: 2, Harga 20000
-	Nama Item: Pasta Gigi,  qty:3, harga: 15000

### Test #2 (Berhasil)

Ternyata Customer salah membeli salah satu item dari belanjaan yang sudah ditambahkan, maka Customer menggunakan method delete_item() untuk menghapus item. Item yang ingin dihapuskan adalah Pasta Gigi:

### Test #3 (Berhasil)

Ternyata setelah dipikir-pikir Customer salah memasukkan item yang ingin dibelanjakan! Daripada menghapusnya satu-satu, maka Customer cukup menggunakan method reset_transaction() untuk menghapus semua item yang sudah ditambahkan.

### Test #4 (Berhasil)

Setelah Customer selesai berbelanja, akan menghitung total belanja yang harus dibayarkan menggunakan method total_price(). Sebelum mengeluarkan output total belanja akan menampilkan item-item yang dibeli.

## Conclusion and Future Work
System cashier yang disiapkan sudah dapat memenuhi semua kebutuhan fungsi yang diharapkan dalam Requirement dan Features. Tambahan feature yang diberikan semata-mata ditambahkan untuk kemudahan Customer melakukan entry terhadap daftar belanja. 

### Pengembangan
> System ini akan dapat dikembangkan lebih baik dengan kelengkapan akses database yang melengkapi pilihan-pilihan bagi Customer dan menambah kesempatan bagi Supermarket untuk menawarkan produk yang lebih banyak. <br>
> System ini juga dapat dikembangkan untuk memiliki tampilan yang lebih baik dengan kemampuan untuk mengakses gambar dan deskripsi produk yang lebih informatif bagi pembeli. <br>

### Perbaikan
> System ini dapat dikembangkan dengan akses os sehingga dapat menggunakan file py seperty yang diharapkan
