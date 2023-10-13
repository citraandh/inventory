# Iventory App: Pattiserie Page

Nama        : Citra Andini Hermawan

NPM         : 2206830012

Kelas       : PBP D

Adaptable   : https://inventory-candh.adaptable.app/

# Pertanyaan Tugas 2
## Pengimplementasian checklist
    Dalam pengerjaan Tugas 2 ini, steps yang saya lakukan mirip dengan tutorial 0 dan 1
    * Pertama, saya membuat direktori lokal baru di laptop yang bernama inventory_app. Kemudian, mengkonfigurasi awal git dengan perintah git init.
    * Lalu, saya membuat repositori baru di Github yang bernama inventory dan menghubungkannya dengan direktori inventory_app lokal.
    * Kemudian, membuat proyek django inventory_app dan menambahkan file .gitignore di direktori inventory_app lokal. Lalu, saya mendeploy aplikasinya.
    * Membuat aplikasi main dalam proyek inventory_app dan menambahkan 'main' ke dalam INSTALLED_APPS dalam settings,py di proyek inventory_app untuk mendaftarkan aplikasi main.
    * Membuat model dengan nama Item dengan atribut name, amount, price, dan description.
    *  Melakukan migrasi model dengan makemigration dan migrate.
    * Menampilkan nama aplikasi, nama, dan kelas PBP D dalam template dan views.py dengan membuat fungsi show_main dan memodifikasi templates.
    * Mengonfigurasi routing dengan mengisi urls.py
    * Jalankan proyek Django dengan runserver


## Buatlah bagan yang berisi request client ke web aplikasi berbasis Django beserta responnya dan jelaskan \
![bagan](https://i.postimg.cc/KvYhYR6v/Whats*App*Image*2023*09*13*at*10*04*33.jpg)
\
    Pertama-tama client request di kirim ke urls.py yang diteruskan ke views.Views akan mengakses data models.py dan dikirm kembali ke view. Views akan meneruskan ke html untuk menampilkan hasilnya dan mengirim response ke client.

## Mengapa kita menggunakan virtual environment? Apakah tetap dapat membuat aplikasi web berbasis Django tanpanya?\
Virtual environment dibuat di atas instalasi python yang ada. Kegunaan virtual environment itu sendiri adalah untuk mengontrol packages python atau dependensi yang berbeda untuk berbagai projek. Jadi, apabila projek A membutuhkan package x, tidak akan memperngaruhi projek B yang memiliki requirement/dependensi yang berbeda. Dengan VE, kita juga dapat dengan mudah menghapus dependensi suatu proyek tanpa mempengaruhi OS. Selain itu, VE juga membuat kolaborasi lebih mudah
    Tanpa VE, kita tetap dapat membuat aplikasi berbasis Django. Namun, kemungkinan akan bermasalah lebih besar dan rumit. Hal itu karena VE ada untuk mempermudah software developing. Akan lebih baik apabila kita menggunakan virtual environment.

## Apa itu MVC, MVT, MVVM dan perbedaannya?\
Model-View-Controller (MVC) membagi program menjadi 3 komponen. Ketika membuat aplikasinya,developer harus mengelompokannya ke dalam salah satu dari ketiga komponen itu
        1. Model, yang akan menyimpan data aplikasi. Model bertanggung jawab untuk komunikasi dengan database
        2. View, yaitu Interface yang akan berinteraksi dengan user dan memberikan visualisasi dari data Model
        3. Controller, menghubungkan View ddan Model yang berisi logika aplikasi dan menerima respon user serta memperbarui Model jika diperlukan.

Model-View-Template (MVT)
        1. Model, untuk menyimpan data dan komunikasi dengan database
        2. View, yang mengelola logika presentasi dan mengambil data dari Model dan menerapkan logika UI untuk menentukan apa yang ditampilkan
        3. Template, mengatur tampilan user dan memisahkan html dari logika aplikasi. Template digunakan untuk merancang tampilan yang nantinya diisi data dari model melalui view
    
Model-View-ViewModel(MVVM)\
        Pada MVVM, logika presentasi data (View) dipisahkan dengan logika bisnis utama dari aplikasi.
        1. Model, abstraksi dari sumber*sumber data. Model dan ViewModel bekerja sama untuk menyimpan datanya.
        2. View, untuk memnginformasikan ViewModel aksi user dan tidak mengandung logika aplikasi.
        3. ViewModel, sebagai hubungan antara Model dan View serta menampilakn data yang relevan ke View.
    
    Perbedaan ketiganya:
    * MVC input di Controller dan controller berfungsi sebagai penghubung, MVT View dan Template  terhubung , dan MVVM ViewModel berperan kuat, dapat bekerja sendiri tanpa logika aplikasi dari View
    * Pada MVC sulit untuk membuat perubahan karena ketiga komponen sangat terikat. Pada MVT, perubahan mudah terjadi. Sedangkan pada MVVP, mudah untuk mengubah aplikasi namun apabila logika pengikat datanya terlalu kompleks, akan sulit untuk debug.
    * MVC, cocok untuk projek skala kecil, MVT cocok untuk aplikasi simple dan kompleks, sementara MVVP tidak cocok untuk projek berskala kecil.

# Pertanyaan Tugas 3
=================================================================
## Apa perbedaan antara form POST dan form GET dalam Django?
Get digunakan untuk membaca atau mengambil data dari web server 
    dan mereturn HTTP status code 200 jika data berhasil diambil.
    Method form GET, nilai dapat dilihat langsung dalam URL yang 
    dikirimkan. form GET baiknya digunakan untuk menampilkan data 
    atau mengambil data dari database saja. Tidak disarankan 
    menggunakan form method ini untuk data sensitif.
Post digunakan untuk mengirim data ke server yang akan mereturn 
    HTTP    status code 201 jika berhasil mengirim.
    Method form POST tidak akan menampilkan isi form untuk ditampilkan
    di URL. Oleh karena itu, method ini cocok untuk data sensitif 
    yang membutuhkan keamanan tinggi. Method post digunakan untuk 
    menambah data seperti upload file atau login.

## Apa perbedaan utama antara XML, JSON, dan HTML dalam konteks pengiriman data?
XML dan JSON digunakan untuk menyimpan dan mengirim data sedangkan 
    HTML digunakan untuk mendeskripsikan data atau bagaimana data 
    tersebut ditampilkan. XML berbentuk tree dengan branchnya 
    sedangkan JSON berupa key*value pair seperti dictionary. XML 
    harus menggunakan parser XML sedangkan JSON bisa diparse 
    dengan fungsi standar JavaScript. Karena struktur dan ukuran 
    `filenya, JSON lebih cepat dibandingkan XML.

## Mengapa JSON sering digunakan dalam pertukaran data antara aplikasi web modern?
Karena JSON menyimpan data dengan pasangan key-value (dictionary) dan 
    menggunakan kurung kurawal sebagai penanda. Struktur JSON yang baik 
    membuatnya mudah dibuat dan dibaca. Selain itu, JSON merupakan turunan
    dari JavaSript dan dapat dengan mudah diparse oleh browsers.JSON juga
    cocok atau compatible dengan banyak bahasa pemrograman dan framework,
    serta lebih cepat.

## Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step*by*step (bukan hanya sekadar mengikuti tutorial).
1. Masuk ke direktori utama dengan membuka cmd dan mengetik cd inventory_app.
2. Mengaktifkan virtual environment.
3. Membuka urls.py yang ada dalam folder inventory_app dan memodifikasi                urlpatterns path main/ menjadi ''.
4. Membuat folder templates pada direktori utama dan didalamnya, membuat file html baru dengan nama base.html sebagai template atau kerangka dasar.
5. Membuka settings.py di subdirektori inventory_app dan memodifikasi DIRS dalam TEMPLATES menjadi [BASE_DIR / 'templates'] supaya templatenya diset dari file base.html.

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

## Screenshots Postman

### HTML
![HTML](https://i.postimg.cc/Hkgds416/Screenshot-693.png)

![HTML](https://i.postimg.cc/5NvfVKTH/Screenshot-694.png)

![HTML](https://i.postimg.cc/sg4yBQVs/Screenshot-695.png)

![HTML](https://i.postimg.cc/FKFv0rRc/Screenshot-696.png)

![HTML](https://i.postimg.cc/wxn9nYf8/Screenshot-697.png)

### XML
![XML](https://i.postimg.cc/R00F4Qwj/Screenshot-698.png)

![XML](https://i.postimg.cc/L8DXc0gt/Screenshot-699.png)

### JSON
![JSON](https://i.postimg.cc/VkmvHcvs/Screenshot-700.png)

![JSON](https://i.postimg.cc/yYqkcRzZ/Screenshot-701.png)

![JSON](https://i.postimg.cc/gkvrD0YB/Screenshot-702.png)

### XML ID
![xml_id](https://i.postimg.cc/Kc311NCb/Screenshot-703.png)

### JSON ID
![json_id](https://i.postimg.cc/sXq1nQQb/Screenshot-704.png)'

# Pertanyaan Tugas 4
=================================================================
## Apa itu Django UserCreationForm, dan jelaskan apa kelebihan dan kekurangannya?
   
   UserCreationForm adalah form bawaan Django untuk membuat user baru yang dapat mengakses web kita. Memiliki 3 fields yaitu username, password, dan password (confirmation).

   Kelebihannya:
   1. Mudah digunakan karena user tidak perlu memulai dari awal.
   2. Password validation, memastikan password sesuai standar kuat.
   3. Dapat dimodifikasi atau custome sesuai kebutuhan.

   Kekuarangan:
   1. Display terbatas, yang tersedia hanyalah basic. Jika ingin mempercantik, kita harus menambahkannya sendiri.
   2. Fitur terbatas. UserCreationForm hanya enyediakan username dan password sehingga jika membutuhkan informasi tambahan seperti email dan verifikasi captcha, kita harus menambahkannya secara manual.


## Apa perbedaan antara autentikasi dan otorisasi dalam konteks Django, dan mengapa keduanya penting
    
    Autentikasi akan memverifikasi apakah user adalah dirinya sendiri (identitas) sedangkan Otorisasi mengarah ke wewenang atau akses yang dimiliki user tersebut. Keduanya penting untuk menjaga keamanan dan integritas data karena user hanya dapat mengakses yang diperlukan.

 ## Apa itu cookies dalam konteks aplikasi web, dan bagaimana Django menggunakan cookies untuk mengelola data sesi pengguna?
    
    Cookies adalah kumpulan informasi yang berisi aktivitas yang dilakukan ketika menelusuri website. Cookies diterima komputer dari suatu website dan mengirimkan kembali ke web yang dikunjungi. Biasa digunanakan untuk mengenali user yang login dan menyimpan preferensi user.

    Django memungkinkan user untuk membuat dan mengatur cookies dengan mengimport 'HttpResponse', membaca cookie dengan 'request.COOKIES.get', dan menghapus cookie.

    Adapula Django menggunakan cookie yang berisi session id unik untuk mengidentifikasi setiap browser dan session dalam suatu website. Data dari session disimpan di database website by default, tapi juga bisa ditempat lain. Gunanya adalah untuk holding state sehingga kita tidak perlu login lagi ketika berpindah halaman di website yang sama.

## Apakah penggunaan cookies aman secara default dalam pengembangan web, atau apakah ada risiko potensial yang harus diwaspadai?
    Tidak selalu aman, ada beberapa risiko potensial yang harus diwaspadai, yaitu:
    1. Privasi. Cookies dapat mencatat aktivitas user di seluruh website. Oleh karena itu, dapat mengancam privasi user jika tidak diatur dengan baik.
    2. Serangan seperti Cross Site Request Forgery (CSRF) dan Cross Site Scripting. Maka dari itu, kita perlu memberikan perlindungan seperti token csrf dan menggunakan HTTPS.

## Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)!
    
**Mengimplementasikan fungsi registrasi, login, dan logout untuk memungkinkan pengguna untuk mengakses aplikasi sebelumnya dengan lancar**
    Masuk ke direktori utama dengan membuka cmd dan mengetik cd inventory_app .
    Mengaktifkan virtual environment dengan mengetik 'env\Scripts\activate.bat' .
    Membuka main>views.py dan mengimport redirect, UserCreationForm, messages, authenticate, login, logout.
    Di dalamnya, membuat fungsi register, login_user, dan logout_user.
    Membuat file html bernama register dan login pada main> templates.
    Membuka main>views.py dan mengimport login_require untuk merestriksi akses.
        'from django.contrib.auth.decorators import login_required'
    Menambahkan kode @login_required(login_url='/login') di atas fungsi show_main yang berguna agar main hanya bisa diakses oleh user yang sudah terautentikasi.
    Tambahkan import HttpResponseRedirect, reverse, dan datetime 
    Modifikasi fugsi login_user pada blok if user is not None menjadi
    ```
    if user is not None:
    login(request, user)
    response = HttpResponseRedirect(reverse("main:show_main")) 
    response.set_cookie('last_login', str(datetime.datetime.now()))
    return response
    ```
    Tambahkan baris ''last_login': request.COOKIES['last_login']' ke dalam variabel context di fungsi show_main.
    Ubah fungsi logout_user menjadi
    ```
    def logout_user(request):
        logout(request)
        response = HttpResponseRedirect(reverse('main:login'))
        response.delete_cookie('last_login')
        return response
    ```
    Buka main.html dan tambahkan kode di bawah diantara tombol logout dan tabel
        ` <h5>Sesi terakhir login: {{ last_login }}</h5>`
        
**Membuat dua akun pengguna dengan masing-masing tiga dummy data menggunakan model yang telah dibuat pada  aplikasi sebelumnya untuk setiap akun di lokal.**
    
![user1](https://i.postimg.cc/t4MHDY1d/Whats-App-Image-2023-09-27-at-10-46-18.jpg)

![user2](https://i.postimg.cc/WzFZFDJ9/Whats-App-Image-2023-09-27-at-10-37-17.jpg)

**Menghubungkan Item dengan User**
1. Buka main>models.py dan import User.
2. Tambahkan user = models.ForeignKey(User, on_delete=models.CASCADE) dalam model Item untuk mengasosiasikan produk dengan seorang user.
3. Buka main>views.py dan modifikasi fungsi create_product menjadi
    ```
    def create_product(request):
        form = ProductForm(request.POST or None)

        if form.is_valid() and request.method == "POST":
            product = form.save(commit=False)
            product.user = request.user
            product.save()
            return HttpResponseRedirect(reverse('main:show_main'))
    ```
4. Ubah kode dalam fungsi show_main bagian context 'name' menjadi
    ```
        'name': request.user.username,
    ```
    untuk menampilkan username yang login pada page main.

5. Lakukan migrasi model dengan mengetik pada cmd
    ```
    python manage.py makemigrations
    ```
    untuk membuat file migrasi berisi perubahan model dan
    ```
    python manage.py migrate
    ```
    untuk mengaplikasikan perubahan model`

Terakhir, git add, commit, push ke github

# Pertanyaan Tugas 5
## Jelaskan manfaat dari setiap element selector dan kapan waktu yang tepat untuk menggunakannya
### Element Selector
Memilih semua instance elemen dengan nama tag yang sama. Tepat digunakan ketika ingin menerapkan style ke semua elemen dengan nama tag tertentu di webpage.
```
h5 {
    font-size: 16px;
    font-family: Georgia;
    color: #AA6EB3;
    background-color: white;
    padding: 5px;
    border: 1px solid #AA6EB3;
    margin: 10px;
    } 
```
### Class Selector
Memilih semua elemen dengan atribut class yang sesuai. Tepat digunakan ketika ingin menerapkan style ke grup elemen yang memiliki kelas yang sama. Kita dapat memberikan style yang berbeda kepada elemen yang memiliki kelas berbeda dalam elemen dengan tag yang sama.
```
.register-link {
    color: #fff; 
    font-weight: bold;
    margin-top: 20px;
}
```

### ID Selector
Memilih elemen dengan atribut id yang sesuai. Tepat digunakan ketika ingin merujuk dan memberikan style khusus ke elemen tertentu.
```
<header id="main-header">
<h1>Halaman Utama</h1>
</header>
```

```
#main-header {
    background-color: #333;
    color: white;
    padding: 10px;
}
```

## Jelaskan HTML5 Tag yang kamu ketahui.
`<header>` untuk mendefinisikan bagian atas section.
`<footer>` untuk mendefinisikan bagian bawah section (misalnya informasi penulis).
`<audio>` untuk memasukkan audio ke halaman web.
`<video>` untuk memasukkan video seperti cuplikan film.
`<time>` untuk menampilkan tanggal atau waktu.
`<article>` untuk mendefinisikan konten independen di suatu dokumen, seperti blog, majalah, atau artikel lainnya.
`<nav>` untuk menandai bagian navigasi atau tautan ke halaman lain di website.

## Jelaskan perbedaan antara margin dan padding.
Margin adalah ruang di luar batas elemen HTML, sedangkan padding adalah ruang di dakam elemen HTML. Margin digunakan untuk memgatur jarak antara elemen dengan elemen lain di sekitarnya, sementara padding digunakan untuk mengatur jarak antara isi/konten elemen dengan batas elemen tersebut. Margin tidak berwarna, sedangkan padding dapat diatur warnanya. Elemen di luar margin tidak dapat menembus batas margin, sementara elemen di dalam padding dapat muncul di dalam ruang padding tersebut.

## Jelaskan perbedaan antara framework CSS Tailwind dan Bootstrap. Kapan sebaiknya kita menggunakan Bootstrap daripada Tailwind, dan sebaliknya?
Tailwind CSS mengandalkan penggunaan kelas-kelas utilitas yang telah ditentukan sebelumnya untuk membangun tampilan, sedangkan Bootstrap menyediakan gaya dan komponen yang telah siap pakai. Tailwind CSS memiliki file CSS yang lebih kecil dan memberikan tingkat fleksibilitas yang tinggi, memungkinkan developer untuk lebih bebas mengatur tampilan sesuai kebutuhan proyek mereka. Namun, pembelajaran Tailwind CSS dapat lebih curam karena memerlukan pemahaman yang kuat tentang berbagai kelas utilitas yang tersedia. 

Di sisi lain, Bootstrap menyediakan tampilan yang lebih konsisten di seluruh proyek dan memiliki pembelajaran yang lebih cepat, terutama bagi pemula yang dapat memulai dengan komponen yang sudah siap pakai. Pilihan antara Bootstrap dan Tailwind tergantung pada kebutuhan proyek dan preferensi pengembang.

## Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
Tugas kali ini, saya memodifikasi layout atau tampilan dari web yang telah dibuat sebelumnya: 
Tema web yaang dibuat adalah bernuansa Ungu dengan pink dan kuning. 

1. **login.html**: Halaman ini digunakan untuk login ke aplikasi. Adapun di dalamnya:
   - Terdapat form login dengan input untuk username dan password.
   - Terdapat tombol "Login" untuk mengirimkan data login.
   - Terdapat juga link "Register Now" untuk mengarahkan pengguna ke halaman pendaftaran jika mereka belum memiliki akun.
   
2. **register.html**: Halaman ini digunakan untuk membuat akun baru jika pengguna belum memiliki akun. Page ini berisi:
   - Form pendaftaran dengan berbagai informasi yang harus diisi oleh pengguna.
   - Tombol "Daftar" untuk mengirimkan data pendaftaran.
   
3. **main.html**: Halaman utama dari aplikasi setelah login. Didalamnya:
   - Menampilkan judul halaman "Patisserie Page" dengan hiasan emoji 🧁.
   - Menampilkan nama dan kelas pengguna dalam satu kotak.
   - Menampilkan daftar item (produk) dalam bentuk kartu (tidak menggunakan framework) dengan informasi seperti nama, harga, jumlah, deskripsi, dan tanggal penambahan.
   - Menampilkan waktu last login.
   - Terdapat tombol "Add New Product" yang mengarahkan pengguna ke halaman untuk menambahkan produk baru.
   - Terdapat tombol "Logout" untuk keluar dari akun.
   
4. **create product.html**: Halaman ini digunakan untuk menambahkan produk baru ke dalam aplikasi.
   - Menampilkan judul "New Product".
   - Terdapat form untuk mengisi informasi produk seperti nama, harga, jumlah, deskripsi, dan lainnya.
   - Terdapat tombol "Add Product" untuk mengirimkan data produk yang baru ditambahkan.

Semua halaman menggunakan CSS untuk mengatur tampilan dan style elemen-elemen HTML sehingga tampilan keseluruhan aplikasi terlihat menarik dan konsisten.

* Menambahkan `<style` CSS untuk mengatur tampilan termasuk background, font, dan lainnya.
* Mengatur tampilan dengan tema ungu dan terstruktur rapih.

BONUS
![user1](https://i.postimg.cc/FsQGFb87/Screenshot-778.png)

# Pertanyaan Tugas 5

## Jelaskan perbedaan antara asynchronous programming dengan synchronous programming.
Sinkronus artinya eksekusi setiap operasi bergantung pada status selesainya operasi sebelum. Jika operasi sebelumnya belum selesai, maka akan dilakukan blocking sehingga tidak bisa meneruskannya. User harus menunggu suatu data selesai diupload baru melakukan action lainnya.

Asinkronus artinya eksekusi satu operasi tidak bergantung pada aksi lainnya. User bisa berinteraksi dengan website, tanpa harus menunggu satu aksi selesai (misalnya upload data).

Adapun perbedannya antara lain:
    - Asinkronus adalah multi-thread, yang berarti operasi atau program dapat berjalan secara paralel.
    - Sinkronus adalah single-thread, sehingga hanya satu operasi atau program yang berjalan pada satu waktu.
    - Asinkronus adalah non-blocking, yang berarti ia akan mengirimkan banyak permintaan ke server.
    - Sinkronus blocking, ia hanya akan mengirimkan satu permintaan ke server pada satu waktu dan menunggu sampai permintaan tersebut dijawab oleh server.
    - Sinkronus lebih lambat, metodis, dan lebih mudah diikuti.

## Dalam penerapan JavaScript dan AJAX, terdapat penerapan paradigma event-driven programming. Jelaskan maksud dari paradigma tersebut dan sebutkan salah satu contoh penerapannya pada tugas ini.
Paradigma event-driven programming artinya pemrograman yang berfokus pada pengelolaan event atau peristiwa dalam aplikasi. Dalam JavaScript dan AJAX, sering digunakan karena aplikasi web bergantung pada respon terhadap event. Contohnya adalah klik mouse, tekan tombol keyboard, atau bisa juga meminta data dari server melalui AJAX. Hal penting dari paradigma ini adalah:
- Pentingnya event seperti klik mouse, tombol keyboard, atau bisa juga mengirimkan pesan.
- Event Handler, respon ketika suatu event terjadi. Biasanya berupa fungsi.
- Non blocking, artinya web tidak perlu menunggu satu aksi selesai sebelum melanjutkan eksekusi aksi berikutnya. Web akan tetap responsif dan dinamis.'

## Jelaskan penerapan asynchronous programming pada AJAX.
Asynchronous programming dalam konteks AJAX mencerminkan penggunaan teknik yang memungkinkan kode dieksekusi secara asinkron, tanpa harus menghentikan eksekusi utama dari program. Praktik ini memungkinkan halaman web untuk tetap responsif dan berinteraksi dengan pengguna tanpa menunggu tugas yang memerlukan waktu, seperti permintaan ke server, untuk selesai. Penerapan asynchronous programming dalam AJAX melibatkan penggunaan fitur-fitur seperti async dan await. Kita dapat mendefinisikan fungsi sebagai async dengan menambahkan kata kunci `async` sebelum kata kunci fungsi, yang mengindikasikan bahwa fungsi tersebut akan beroperasi secara asinkronus dan dapat menggunakan `await` untuk menunggu hasil dari operasi asinkronus lainnya. Dengan kedua fungsi tersebut, kita dapat mengendalikan alur eksekusi dengan lebih efisien.

## Pada PBP kali ini, penerapan AJAX dilakukan dengan menggunakan Fetch API daripada library jQuery. Bandingkanlah kedua teknologi tersebut dan tuliskan pendapat kamu teknologi manakah yang lebih baik untuk digunakan.
Fetch API:
- Lebih modern.
- Kita tidak perlu menambahkan library tambahan sehingga kode lebih ringan dan bersih.
- Fleksibel, memiliki support untuk berbagai jenis HTTP request.
- Fetch API menggunakan Promises, yang membuatnya lebih mudah untuk mengelola permintaan asinkron dan menghindari callback hell.
jQuery:
- Menyediakan abstraksi tingkat tinggi untuk berbagai tugas, termasuk AJAX.
- Dukungan Cross-Browser.
- Dokumentasi banyak sehingga mudah dipelajari.

Fetch API adalah pilihan yang lebih modern dan disarankan untuk aplikasi web modern, memberikan kontrol lebih besar dan kode yang lebih bersih. jQuery, sementara lebih mudah diimplementasikan dan cocok untuk pemula, mungkin menambah overhead jika digunakan hanya untuk fungsi AJAX. Pemilihan tergantung pada kebutuhan proyek dan preferensi. Dalam banyak kasus, Fetch API dengan JavaScript lebih efisien.

## Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
- Buat fungsi get product json di views.py
- Buat fungsi add_product_ajax 
- Routing
- Menampilkan button Add Product by AJAX