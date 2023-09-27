Nama        : Citra Andini Hermawan

NPM         : 2206830012

Kelas       : PBP D

# Pertanyaan Tugas 4
=================================================================\
## Apa itu Django UserCreationForm, dan jelaskan apa kelebihan dan kekurangannya?
   
   UserCreationForm adalah form bawaan Django untuk membuat user baru yang dapat mengakses web kita. Memiliki 3 fields yaitu username, password, dan password (confirmation).

   Kelebihannya:
   1. Mudah digunakan karena user tidak perlu memulai dari awal.
   2. Password validation, memastikan password sesuai standar kuat.
   3. Dapat dimodifikasi atau custome sesuai kebutuhan.

   Kekuaranga:
   1. Display terbatas, yang tersedia hanyalah basic. Jika ingin mempercantik, kita harus menambahkannya sendiri.
   2. Fitur terbatas. UserCreationForm hanya enyediakan username dan password sehingga jika membutuhkan informasi tambahan seperti email dan verifikasi captcha, kita harus menambahkannya secara manual.


## Apa perbedaan antara autentikasi dan otorisasi dalam konteks Django, dan mengapa keduanya penting?
    
    Autentikasi akan memverifikasi apakah user adalah dirinya sendiri (identitas) sedangkan Otorisasi mengarah ke wewenang atau akses yang dimiliki user tersebut. Keduanya penting untuk menjaga keamanan dan integritas data karena user hanya dapat mengakses yang diperlukan.

 ## Apa itu cookies dalam konteks aplikasi web, dan bagaimana Django menggunakan cookies untuk mengelola data sesi pengguna?
    
    Cookies adalah kumpulan informasi yang berisi aktivitas yang dilakukan ketika menelusuri website. Cookies diterima komputer dari suatu website dan mengirimkan kembali ke web yang dikunjungi. Biasa digunanakan untuk mengenali user yang login dan menyimpan preferensi user.

    Django memungkinkan user untuk membuat dan mengatur cookies dengan mengimport 'HttpResponse', membaca cookie dengan 'request.COOKIES.get', dan menghapus cookie.

    Adapula Django menggunakan cookie yang berisi session id unik untuk mengidentifikasi setiap browser dan session dalam suatu website. Data dari session disimpan di database website by default, tapi juga bisa ditempat lain. Gunanya adalah untuk *holding state* sehingga kita tidak perlu login lagi ketika berpindah halaman di website yang sama.

## Apakah penggunaan cookies aman secara default dalam pengembangan web, atau apakah ada risiko potensial yang harus diwaspadai?
    
    Tidak selalu aman, ada beberapa risiko potensial yang harus diwaspadai, yaitu:
    1. Privasi. Cookies dapat mencatat aktivitas user di seluruh website. Oleh karena itu, dapat mengancam privasi user jika tidak diatur dengan baik.
    2. Serangan seperti Cross Site Request Forgery (CSRF) dan Cross Site Scripting. Maka dari itu, kita perlu memberikan perlindungan seperti token csrf dan menggunakan HTTPS.

## Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)!
    
    **Mengimplementasikan fungsi registrasi, login, dan logout untuk memungkinkan pengguna untuk mengakses aplikasi sebelumnya dengan lancar**

    1. Masuk ke direktori utama dengan membuka cmd dan mengetik cd inventory_app .
    2. Mengaktifkan virtual environment dengan mengetik 'env\Scripts\activate.bat' .
    3. Membuka main>views.py dan mengimport redirect, UserCreationForm, messages, authenticate, login, logout.
    4. Di dalamnya, membuat fungsi register, login_user, dan logout_user.
    5. Membuat file html bernama register dan login pada main> templates.
    6. Membuka main>views.py dan mengimport login_require untuk merestriksi akses.
        'from django.contrib.auth.decorators import login_required'
    7. Menambahkan kode @login_required(login_url='/login') di atas fungsi show_main yang berguna agar main hanya bisa diakses oleh user yang sudah terautentikasi.
    8. Tambahkan import HttpResponseRedirect, reverse, dan datetime 
    9. Modifikasi fugsi login_user pada blok if user is not None menjadi
        '''
        if user is not None:
        login(request, user)
        response = HttpResponseRedirect(reverse("main:show_main")) 
        response.set_cookie('last_login', str(datetime.datetime.now()))
        return response
        '''
    10. Tambahkan baris ''last_login': request.COOKIES['last_login']' ke dalam variabel context di fungsi show_main.
    11. Ubah fungsi logout_user menjadi
        '''
        def logout_user(request):
            logout(request)
            response = HttpResponseRedirect(reverse('main:login'))
            response.delete_cookie('last_login')
            return response
        '''
    12. Buka main.html dan tambahkan kode di bawah diantara tombol logout dan tabel
        ' <h5>Sesi terakhir login: {{ last_login }}</h5>'
        
    **Membuat dua akun pengguna dengan masing-masing tiga dummy data menggunakan model yang telah dibuat pada  
    aplikasi sebelumnya untuk setiap akun di lokal.**
    
    ![user1](https://i.postimg.cc/t4MHDY1d/Whats-App-Image-2023-09-27-at-10-46-18.jpg)

    ![user2](https://i.postimg.cc/WzFZFDJ9/Whats-App-Image-2023-09-27-at-10-37-17.jpg)

    **Menghubungkan Item dengan User**
    1. Buka main>models.py dan import User.
    2. Tambahkan user = models.ForeignKey(User, on_delete=models.CASCADE) dalam model Item untuk mengasosiasikan produk dengan seorang user.
    3. Buka main>views.py dan modifikasi fungsi create_product menjadi
        '''
        def create_product(request):
            form = ProductForm(request.POST or None)

            if form.is_valid() and request.method == "POST":
                product = form.save(commit=False)
                product.user = request.user
                product.save()
                return HttpResponseRedirect(reverse('main:show_main'))
        '''
    4. Ubah kode dalam fungsi show_main bagian context 'name' menjadi
        '''
            'name': request.user.username,
        '''
        untuk menampilkan username yang login pada page main.

    5. Lakukan migrasi model dengan mengetik pada cmd
        '''
        python manage.py makemigrations
        '''
        untuk membuat file migrasi berisi perubahan model dan
        '''
        python manage.py migrate
        '''
        untuk mengaplikasikan perubahan model`
    
    Terakhir, git add, commit, push ke github