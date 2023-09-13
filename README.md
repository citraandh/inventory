Nama        : Citra Andini Hermawan

NPM         : 2206830012

Kelas       : PBP D

Adaptable   : https://inventory-candh.adaptable.app/

Pengimplementasian checklist
    Dalam pengerjaan Tugas 2 ini, steps yang saya lakukan mirip dengan tutorial 0 dan 1.
    - Pertama, saya membuat direktori lokal baru di laptop yang bernama inventory_app. Kemudian, mengkonfigurasi awal git dengan perintah git init.
    - Lalu, saya membuat repositori baru di Github yang bernama inventory dan menghubungkannya dengan direktori inventory_app lokal.
    - Kemudian, membuat proyek django inventory_app dan menambahkan file .gitignore di direktori inventory_app lokal. Lalu, saya mendeploy aplikasinya.
    - Membuat aplikasi main dalam proyek inventory_app dan menambahkan 'main' ke dalam INSTALLED_APPS dalam settings,py di proyek inventory_app untuk mendaftarkan aplikasi main.
    - Membuat model dengan nama Item dengan atribut name, amount, price, dan description.
    -  Melakukan migrasi model dengan makemigration



Mengapa kita menggunakan virtual environment? Apakah tetap dapat membuat aplikasi web berbasis Django tanpanya?
    Virtual environment dibuat di atas instalasi python yang ada. Kegunaan virtual environment itu sendiri adalah untuk mengontrol packages python atau dependensi yang berbeda untuk berbagai projek. Jadi, apabila projek A membutuhkan package x, tidak akan memperngaruhi projek B yang memiliki requirement/dependensi yang berbeda. Dengan VE, kita juga dapat dengan mudah menghapus dependensi suatu proyek tanpa mempengaruhi OS. Selan itu, CE juga membuat kolaborasi lebih mudah.
    
    Tanpa VE, kita tetap dapat membuat aplikasi berbasis Django. Namun, kemungkinan akan bermasalah lebih besar dan rumit. Hal itu karena VE ada untuk mempermudah software developing. Akan lebih baik apabila kita menggunakan virtual environment.

Apa itu MVC, MVT, MVVM dan perbedaannya?
    Model-View-Controller (MVC) membagi program menjadi 3 komponen. Ketika membuat aplikasinya,developer harus mengelompokannya ke dalam salah satu dari ketiga komponen itu.
        1. Model, yang akan menyimpan data aplikasi. Model bertanggung jawab untuk komunikasi dengan database.
        2. View, yaitu Interface yang akan berinteraksi dengan user dan memberikan visualisasi dari data Model.
        3. Controller, menghubungkan View ddan Model yang berisi logika aplikasi dan menerima respon user serta memperbarui Model jika diperlukan.
    Model-View-Template (MVT)
        1. Model, untuk menyimpan data dan komunikasi dengan database.
        2. View, yang mengelola logika presentasi dan mengambil data dari Model dan menerapkan logika UI untuk menentukan apa yang ditampilkan.
        3. Template, mengatur tampilan user dan memisahkan html dari logika aplikasi. Template digunakan untuk merancang tampilan yang nantinya diisi data dari model melalui view.
    Model-View-ViewModel(MVVM)
        Pada MVVM, logika presentasi data (View) dipisahkan dengan logika bisnis utama dari aplikasi.
        1. Model, abstraksi dari sumber-sumber data. Model dan ViewModel bekerja sama untuk menyimpan datanya.
        2. View, untuk memnginformasikan ViewModel aksi user dan tidak mengandung logika aplikasi.
        3. ViewModel, sebagai hubungan antara Model dan View serta menampilakn data yang relevan ke View.
    Perbedaan ketiganya
    - MVC input di Controller, MVT entry pointnya View, dan MVVM masuk ke aplikasi dan menerima input di View.
    - MVC View tidak mengetahui tentang Controller, MVP View memiliki referensi ke Presenter, dan pada MVVM View memiliki referensi ke ViewModel.
    - Pada MVC sulit untuk membuat perubahan karena ketiga komponene sangat terikat. Pada MVP, perubahan mudah terjadi karena ketiga komponen terkait longgar. Sedangkan pada MVVP, mudah untuk mengubah aplikasi namun apabila logika pengikat datanya terlalu kompleks, akan sulit untuk debug.
    - MVC, cocok untuk projek skala kecil, MVP cocok untuk aplikasi simple dan kompleks, sementara MVVP tidak cocok untuk projek berskala kecil.
    - MVC unit testing terbatas, MVP mudah untuk unit testing tapi hubungan View dan Presenter mungkin membuatnya sedikit bemasalah. Sedangkan pada MVVP, unit testing dapat dilakukan dengan sangat mudah.
    - MVC 1 Controller dapat memilih banyak view sebutuhnya, MVP 1 Presenter mengelola 1 View, MVVP 1 ViewModel dapat memetakan banyak View.
