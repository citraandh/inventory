Nama        : Citra Andini Hermawan

NPM         : 2206830012

Kelas       : PBP D

Pertanyaan =================================================================
Apa perbedaan antara form POST dan form GET dalam Django?

    Get digunakan untuk membaca atau mengambil data dari web server dan me return HTTP status code 200 jika data berhasil diambil.
    
    Post digunakan untuk mengirim data ke server yang akan mereturn HTTP status code 201 jika berhasil mengirim.

Apa perbedaan utama antara XML, JSON, dan HTML dalam konteks pengiriman data?
    
    XML dan JSON digunakan untuk menyimpan dan mengirim data sedangkan HTML digunakan untuk mendeskripsikan data atau bagaimana data tersebut ditampilkan.

Mengapa JSON sering digunakan dalam pertukaran data antara aplikasi web modern?
    
    Karena JSON menyimpan data dengan pasangan key-value (dictionary) dan menggunakan kurung kurawal sebagai penanda. Struktur JSON yang baik membuatnya mudah dibuat dan dibaca. Selain itu, JSON merupakan turunan dari JavaSript dan dapat dengan mudah diparse oleh browsers.JSON juga cocok atau compatible dengan banyak bahasa pemrograman dan framework, serta lebih cepat.

Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
    
    Pertama, masuk ke direktori utama dengan membuka cmd dan mengetik cd inventory_app.

    Kedua, mengaktifkan virtual environment.

    Ketiga, membuka urls.py yang ada dalam folder inventory_app dan memodifikasi urlpatterns path main/ menjadi ''.

    Keempat, membuat folder templates pada direktori utama dan didalamnya, membuat file html baru dengan nama base.html sebagai template atau kerangka dasar.

    Kelima, membuka settings.py di subdirektori inventory_app dan memodifikasi DIRS dalam TEMPLATES menjadi [BASE_DIR / 'templates'] supaya templatenya diset dari file base.html.

    Keenam, membuka main.html(main>templates>main.html) dan memodifikasi sesuai template.

    Ketujuh, membuat form denganmembuat file forms.py di direktori main agar dapat menerima data produk baru.

    Kedelapan, membuka file views.py dan mengimport form.
    Kesembilan, membuat fungsi create_product di views.py yang akan menerima requestdan menghasilkan form untuk menambahkan data.
    
    Kesepuluh, memodifikasi fungsi show_main dalam views.py.

    Kesebelas, mengimport fungsi create_product di urls.py dan menambahkan path urlnya ke dalam urlpatterns agar dapat diakses.

    Keduabelas,membuat file html bernama create_product.html pada templates (main>templates>create_product.html) dan mengisinya untuk menampilkan fields form pada forms.py sebagai tabel dan tombol submit.

    Ketiga belas, membuka main.html dan memodifikasi kodenya agar dapat menampilkan data dalam bentuk tabel dan tombol Add New Product yang akan redirect ke form page.

    Keempat belas, membuka views.py dalam main dan mengimport HttpResponse dan serializers.

    Kelima belas, membuat fungsi yang menerima request dan akan mengembalikan data dalam bentuk XML (show_xml) dan JSON (show_json), serta mengembalikan data berdasarkan ID dalam bentuk XML (show_xml_by_id) dan JSON (show_json_by_id).

    Keenam belas, mengimport fungsi-fungsi diatas ke dalam urls.py pada main dan menambahkan path urlnya ke dalam urlpatterns.

    Terakhir, mengetes apakah data terkirim enggunakan Postman.

