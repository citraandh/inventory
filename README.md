Nama        : Citra Andini Hermawan

NPM         : 2206830012

Kelas       : PBP D

Pertanyaan =================================================================\
Apa perbedaan antara form POST dan form GET dalam Django?

    Get digunakan untuk membaca atau mengambil data dari web server dan 
    mereturn HTTP status code 200 jika data berhasil diambil.
    Method form GET, nilai dapat dilihat langsung dalam URL yang dikirimkan. form GET baiknya digunakan untuk menampilkan data atau mengambil data dari database saja. Tidak disarankan menggunakan form method ini untuk data sensitif.
    
    Post digunakan untuk mengirim data ke server yang akan mereturn HTTP
    status code 201 jika berhasil mengirim.
    Method form POST tidak akan menampilkan isi form untuk ditampilkan di URL. Oleh karena itu, method ini cocok untuk data sensitif yang membutuhkan keamanan tinggi. Method post digunakan untuk menambah data seperti upload file atau login.

Apa perbedaan utama antara XML, JSON, dan HTML dalam konteks pengiriman data?
    
    XML dan JSON digunakan untuk menyimpan dan mengirim data sedangkan 
    HTML digunakan untuk mendeskripsikan data atau bagaimana data 
    tersebut ditampilkan. XML berbentuk tree dengan branchnya sedangkan JSON berupa key-value pair seperti dictionary. XML harus menggunakan parser XML sedangkan JSON bisa diparse dengan fungsi standar JavaScript. Karena struktur dan ukuran filenya, JSON lebih cepat dibandingkan XML.

Mengapa JSON sering digunakan dalam pertukaran data antara aplikasi web modern?
    
    Karena JSON menyimpan data dengan pasangan key-value (dictionary) dan 
    menggunakan kurung kurawal sebagai penanda. Struktur JSON yang baik 
    membuatnya mudah dibuat dan dibaca. Selain itu, JSON merupakan turunan
    dari JavaSript dan dapat dengan mudah diparse oleh browsers.JSON juga
    cocok atau compatible dengan banyak bahasa pemrograman dan framework,
    serta lebih cepat.

Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
    
    1. Masuk ke direktori utama dengan membuka cmd dan mengetik cd inventory_app.
    2. Mengaktifkan virtual environment.
    3. Membuka urls.py yang ada dalam folder inventory_app dan memodifikasi                urlpatterns path main/ menjadi ''.
    4. Membuat folder templates pada direktori utama dan didalamnya, membuat file html baru dengan nama base.html sebagai template atau kerangka dasar.
    5M Membuka settings.py di subdirektori inventory_app dan memodifikasi DIRS dalam TEMPLATES menjadi [BASE_DIR / 'templates'] supaya templatenya diset dari file base.html.

        6. Membuka main.html (main>templates>main.html) dan memodifikasi sesuai template.
        7. Membuat form denganmembuat file forms.py di direktori main agar dapat menerima data produk baru.
        8. Membuka file views.py dan mengimport form.
        9. Membuat fungsi create_product di views.py yang akan menerima request dan menghasilkan form untuk menambahkan data.
        10. Memodifikasi fungsi show_main dalam views.py.

    11. Mengimport fungsi create_product di urls.py dan menambahkan path urlnya ke dalam urlpatterns agar dapat diakses.
    12. embuat file html bernama create_product.html pada templates (main>templates>create_product.html) dan mengisinya untuk menampilkan fields form pada forms.py sebagai tabel dan tombol submit.
    13. Membuka main.html dan memodifikasi kodenya agar dapat menampilkan data dalam bentuk tabel dan tombol Add New Product yang akan redirect ke form page.
    14. Membuka views.py dalam main dan mengimport HttpResponse dan serializers.
    15. Membuat fungsi yang menerima request dan akan mengembalikan data dalam bentuk XML (show_xml) dan JSON (show_json), serta mengembalikan data berdasarkan ID dalam bentuk XML (show_xml_by_id) dan JSON (show_json_by_id).

    16. Mengimport fungsi-fungsi diatas ke dalam urls.py pada main dan menambahkan path urlnya ke dalam urlpatterns.
    17. Mengetes apakah data terkirim menggunakan Postman.

Screenshots Postman

![json_id1]([url=https://postimg.cc/KRJd0TzT][img]https://i.postimg.cc/KRJd0TzT/Screenshot-693.png[/img][/url])

![json_id1]([url=https://postimg.cc/6y9kVc9w][img]https://i.postimg.cc/6y9kVc9w/Screenshot-694.png[/img][/url])

![json_id1]([url=https://postimg.cc/BjbRkvLV][img]https://i.postimg.cc/BjbRkvLV/Screenshot-695.png[/img][/url])

![json_id1]([url=https://postimg.cc/K1WC2ytv][img]https://i.postimg.cc/K1WC2ytv/Screenshot-696.png[/img][/url])

![json_id1]([url=https://postimg.cc/pyYNn4Mq][img]https://i.postimg.cc/pyYNn4Mq/Screenshot-697.png[/img][/url])

![json_id1]([url=https://postimg.cc/MnhxYBPD][img]https://i.postimg.cc/MnhxYBPD/Screenshot-698.png[/img][/url])

![json_id1]([url=https://postimg.cc/Yv4MgR30][img]https://i.postimg.cc/Yv4MgR30/Screenshot-699.png[/img][/url])

![json_id1]([url=https://postimg.cc/jL3RLmyB][img]https://i.postimg.cc/jL3RLmyB/Screenshot-700.png[/img][/url])

![json_id1]([url=https://postimg.cc/w3Vqd7Mq][img]https://i.postimg.cc/w3Vqd7Mq/Screenshot-701.png[/img][/url])

![json]([url=https://postimg.cc/7fZxPwJg][img]https://i.postimg.cc/7fZxPwJg/Screenshot-702.png[/img][/url])

![xml_id]([url=https://postimg.cc/4nZfMzJ2][img]https://i.postimg.cc/4nZfMzJ2/Screenshot-703.png[/img][/url])

![json_id]([url=https://postimg.cc/N98gF0xx][img]https://i.postimg.cc/N98gF0xx/Screenshot-704.png[/img][/url])

