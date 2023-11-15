# Muhammad Fatih Zain

## PBP A - 2206824073

<details open>
<summary>Tugas 8</summary>

# Tugas 8

## Jawaban

### Jelaskan perbedaan antara `Navigator.push()` dan `Navigator.pushReplacement()`, disertai dengan contoh mengenai penggunaan kedua metode tersebut yang tepat! 

Metode `push()` dalam navigasi aplikasi menambahkan rute baru ke tumpukan rute yang ada, menempatkannya di posisi teratas dan menjadikannya rute aktif yang ditampilkan kepada pengguna. Sebaliknya, metode `pushReplacement()` menggantikan rute yang saat ini aktif dengan rute baru, memungkinkan transisi langsung ke rute baru tanpa menambahkan ke tumpukan. Ini berarti bahwa `push()` digunakan untuk menumpuk rute baru di atas yang lama, sedangkan `pushReplacement()` mengganti rute yang ada dengan yang baru tanpa meninggalkan rute lama di tumpukan. Dalam konteks penggunaan, jika pengguna menekan tombol kembali setelah metode `push()` digunakan, mereka akan kembali ke rute sebelumnya, tetapi setelah `pushReplacement()`, tidak akan ada rute sebelumnya untuk kembali kecuali jika ada rute lain di bawahnya di tumpukan.

Contoh `Navigator.push` = Pada website _e-commerce_ ketika pengguna ingin melihat detail dari sebuah produk, maka kita perlu menggunakan `Navigator.push()` untuk membawa user ke halaman detail produk tanpa kehilangan kemampuan untuk kembali ke daftar produk.

Contoh `Navigator.pushReplacement` = Pada proses login, halaman login akan digantikan oleh halaman beranda dalam stack navigasi. Jadi, jika pengguna menekan tombol kembali, mereka tidak akan kembali ke halaman login.


### Jelaskan masing-masing layout widget pada Flutter dan konteks penggunaannya masing-masing!

1. **Container**: Sering digunakan untuk mengatur tampilan sebuah objek. Container bisa memiliki padding, margin, border, dan constraints. Container juga bisa diatur untuk memiliki properti seperti shape, background color, atau box decoration.

2. **Row**: Digunakan untuk menempatkan beberapa widget secara horizontal. Sangat berguna untuk layout yang memerlukan penempatan elemen berdampingan, seperti tombol atau ikon dalam sebuah baris.

3. **Column**: Mirip dengan Row, tetapi untuk penempatan vertikal. Column digunakan untuk menumpuk elemen secara vertikal, seperti daftar informasi atau form input.

4. **Stack**: Memungkinkan elemen-elemen ditumpuk di atas satu sama lain. Stack berguna untuk kasus-kasus di mana kita ingin menempatkan widget di atas widget lain, seperti badge notifikasi di atas ikon atau watermark pada gambar.

5. **Padding**: Digunakan untuk memberikan padding, atau ruang dalam, di sekitar widget lain. Padding sering digunakan untuk memberi ruang antara border sebuah widget dengan kontennya.

6. **Align**: Memungkinkan kita untuk mengatur posisi anak-anaknya dalam dirinya sendiri. Misalnya, Anda bisa menggunakan Align untuk menempatkan sebuah widget di pojok kanan bawah dari sebuah Container.

7. **Expanded**: Digunakan dalam Row, Column, atau Flex untuk memberikan anak-anaknya ruang yang tersedia. Ini berguna untuk membagi ruang secara proporsional di antara elemen-elemen dalam Row atau Column.

8. **Flexible**: Mirip dengan Expanded, tetapi memberikan kontrol yang lebih fleksibel atas pembagian ruang, dengan menggunakan parameter flex.

9. **Wrap**: Secara otomatis memindahkan anak-anaknya ke baris atau kolom berikutnya saat tidak ada cukup ruang. Ini berguna untuk layout yang harus menyesuaikan diri dengan berbagai ukuran layar.

10. **ListView**: Digunakan untuk membuat daftar scrollable. ListView sangat berguna untuk menampilkan daftar item yang panjang atau data yang diambil dari database.

11. **GridView**: Memungkinkan Anda untuk membuat layout grid yang scrollable. GridView cocok untuk menampilkan banyak data dalam bentuk grid, seperti galeri foto atau pilihan produk.

12. **ConstrainedBox**: Memberikan batasan tambahan kepada widget anaknya. Misalnya, Anda bisa membatasi ukuran maksimum widget dengan ConstrainedBox.

13. **SizedBox**: Digunakan untuk memberikan ukuran tetap pada sebuah widget, baik lebar, tinggi, atau keduanya.

14. **AspectRatio**: Digunakan untuk mempertahankan rasio aspek dari widget anaknya. Ini berguna ketika Anda ingin memastikan bahwa sebuah widget mempertahankan rasio lebar dan tinggi tertentu.

15. **FittedBox**: Memastikan bahwa kontennya sesuai dengan ruang yang tersedia, mungkin dengan mengubah skala atau memotong konten.


### Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan jelaskan mengapa kamu menggunakan elemen input tersebut!

1. **TextFormField** untuk `Nama Item`
  - **Alasan Penggunaan** : Elemen input ini digunakan untuk mengumpulkan nama item yang akan ditambahkan. Nama adalah identifikasi dasar dari setiap item dan biasanya merupakan field yang wajib diisi, sehingga memiliki validator untuk memastikan bahwa input tidak kosong.

2. **TextFormField** untuk `Jumlah Item`
  - **Alasan Penggunaan** : Elemen ini digunakan untuk mengumpulkan informasi tentang jumlah atau kuantitas item. Input ini diubah menjadi tipe integer `(int.parse(value!))` karena jumlah item biasanya diwakili dalam bentuk angka. Validator juga memastikan bahwa input tidak kosong dan merupakan angka yang valid.

3. **TextFormField** untuk `Deskripsi Item`
  - **Alasan Penggunaan** : Elemen ini digunakan untuk mengumpulkan deskripsi tambahan tentang item. Deskripsi membantu dalam memberikan informasi lebih lanjut tentang item. Validator memastikan bahwa deskripsi tidak kosong untuk memastikan bahwa setiap item memiliki informasi yang cukup.


### Bagaimana penerapan clean architecture pada aplikasi Flutter?

Penerapan clean architecture pada aplikasi Flutter melibatkan pemisahan kode menjadi lapisan yang berbeda dengan tanggung jawab yang terpisah. Ini membantu dalam membuat kode yang lebih terorganisir, mudah untuk diuji, dan mudah untuk dikelola. Berikut ini adalah lapisan-lapisan umum dalam clean architecture yang bisa diaplikasikan pada Flutter :
  1. **Presentation Layer** : Lapisan yang berinteraksi langsung dengan pengguna, akan terbuat widget dan screen yang membentuk UI aplikasi. Lapisan ini juga akan mengandung logic untuk mengontrol state UI seperti `StatefulWidget` dan `StatelessWidget`.
  2. **Domain Layer (Business Logic)** : Ini adalah inti dari aplikasi Anda. Lapisan domain berisi entitas (atau model) yang murni yang tidak bergantung pada lapisan lain dan mewakili konsep-konsep bisnis aplikasi.
  3. **Data Layer** : Lapisan ini bertanggung jawab untuk mengakses data dari berbagai sumber seperti jaringan, cache lokal, atau database. Ini akan mengimplementasikan _repositories_ yang didefinisikan di lapisan domain dan biasanya akan memiliki dua sub-lapisan, yaitu :
    - **Data Sources** : Sumber data aktual seperti API, database lokal, atau storage lokal.
    - **Repositories Implementations** : Implementasi dari abstraksi repository yang didefinisikan di lapisan domain. Repositori ini akan memutuskan dari mana harus mengambil data (misalnya, dari cache atau API).


### Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial)

  1. Membuat minimal satu halaman baru pada aplikasi, yaitu halaman formulir tambah item baru.
    - Buat file baru `shoplist_form.dart` pada direktori `peti_library/lib`. Kemudian isi dengan :

    ```
    import 'package:flutter/material.dart';
    import 'package:stock_els/widgets/left_drawer.dart';

    class ShopFormPage extends StatefulWidget {
        const ShopFormPage({super.key});

        @override
        State<ShopFormPage> createState() => _ShopFormPageState();
    }

    class _ShopFormPageState extends State<ShopFormPage> {
        @override
        Widget build(BuildContext context) {
            return Placeholder();
        }
    }
    ```

    - Memakai minimal tiga elemen input, yaitu `name`, `amount`, `description`. Tambahkan elemen input sesuai dengan model pada aplikasi tugas Django yang dibuat sebelumnya. Lakukan dengan mengubah Placeholder pada `_ShopFormPageState` di `shoplist_form.dart` dengan kode berikut untuk ketiga elemen :

    ```
    class _ShopFormPageState extends State<ShopFormPage> {
    final _formKey = GlobalKey<FormState>();
    String _name = "";
    int _amount = 0;
    String _description = "";

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(
          title: const Center(
            child: Text(
              'Form Tambah Item',
            ),
          ),
          backgroundColor: Colors.indigo,
          foregroundColor: Colors.white,
        ),
        drawer: const LeftDrawer(),
        body: Form(
            key: _formKey,
            child: SingleChildScrollView(
                child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: TextFormField(
                    decoration: InputDecoration(
                      hintText: "Nama Item",
                      labelText: "Nama Item",
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.circular(5.0),
                      ),
                    ),
                    onChanged: (String? value) {
                      setState(() {
                        _name = value!;
                      });
                    },
                    validator: (String? value) {
                      if (value == null || value.isEmpty) {
                        return "Nama tidak boleh kosong!";
                      }
                      return null;
                    },
                  ),
                ),
                Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: TextFormField(
                    decoration: InputDecoration(
                      hintText: "Jumlah",
                      labelText: "Jumlah",
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.circular(5.0),
                      ),
                    ),
                    onChanged: (String? value) {
                      setState(() {
                        _amount = int.parse(value!);
                      });
                    },
                    validator: (String? value) {
                      if (value == null || value.isEmpty) {
                        return "Harga tidak boleh kosong!";
                      }
                      if (int.tryParse(value) == null) {
                        return "Harga harus berupa angka!";
                      }
                      return null;
                    },
                  ),
                ),
                Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: TextFormField(
                    decoration: InputDecoration(
                      hintText: "Deskripsi",
                      labelText: "Deskripsi",
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.circular(5.0),
                      ),
                    ),
                    onChanged: (String? value) {
                      setState(() {
                        _description = value!;
                      });
                    },
                    validator: (String? value) {
                      if (value == null || value.isEmpty) {
                        return "Deskripsi tidak boleh kosong!";
                      }
                      return null;
                    },
                  ),
                ),
              ]
            )
          )
        )
      )
    }
    }   
    ```    

    - Memiliki sebuah tombol `Save`. Buat tombol ini dengan menambahkan `Align` pada `_ShopFormPageState` di `shoplist_form.dart`.
    
    ```
    Align(
      alignment: Alignment.bottomCenter,
      child: Padding(
        padding: const EdgeInsets.all(8.0),
        child: ElevatedButton(
          style: ButtonStyle(
            backgroundColor: MaterialStateProperty.all(Colors.indigo),
          ),
          onPressed: () {
            if (_formKey.currentState!.validate()) {
              showDialog(
                context: context,
                builder: (context) {
                  return AlertDialog(
                    title: const Text('Item berhasil tersimpan'),
                    content: SingleChildScrollView(
                      child: Column(
                        crossAxisAlignment: CrossAxisAlignment.start,
                        children: [
                          Text('Nama: $_name'),
                          Text('Harga: $_amount'),
                          Text('Deskripsi: $_description'),
                        ],
                      ),
                    ),
                    actions: [
                      TextButton(
                        child: const Text('OK'),
                        onPressed: () {
                          Navigator.pop(context);
                        },
                      ),
                    ],
                  );
                },
              );
              _formKey.currentState!.reset();
            }
          },
          child: const Text(
            "Save",
            style: TextStyle(color: Colors.white),
          ),
        ),
      ),
    ),
    ```
    - Setiap elemen input di formulir juga harus divalidasi dengan ketentuan sebagai berikut:
      - Setiap elemen input tidak boleh kosong.

      ```
      validator: (String? value) {
        if (value == null || value.isEmpty) {
            return "Nama tidak boleh kosong!";
        }
        return null;
      },
      ```

      - Setiap elemen input harus berisi data dengan tipe data atribut modelnya.

      ```
      validator: (String? value) {
        if (value == null || value.isEmpty) {
          return "Jumlah tidak boleh kosong!";
        }
        if (int.tryParse(value) == null) {
          return "Jumlah harus berupa angka!";
        }
        return null;
      },
      ```
  2. Mengarahkan pengguna ke halaman form tambah item baru ketika menekan tombol Tambah Item pada halaman utama.
    - Tambahkan navigator di `shop_card.dart`, hal ini dilakukan agar program akan _redirect_ ke `ShopFormPage()` ketika button ditekan.
    ```
    if (item.name == "Tambah Item") {
      Navigator.push(
          context,
          MaterialPageRoute(builder: (context) => ShopFormPage()),
      );
    }
    ```
    - Tambahkan drawer di `menu.dart`
      ```
      import 'package:stock_els/widgets/left_drawer.dart';
      ...

      drawer: const LeftDrawer(),
      ...
      ```
  3. Memunculkan data sesuai isi dari formulir yang diisi dalam sebuah pop-up setelah menekan tombol Save pada halaman formulir tambah item baru.
    Sudah dicakup diatas, edit class `_ShopFormPageState` di `shoplist_form.dart`. bagian yang memunculkan data sesuai dimulai dari baris kode `onPressed()`.
    ```
    onPressed: () {
      if (_formKey.currentState!.validate()) {
        showDialog(
          context: context,
          builder: (context) {
            return AlertDialog(
              title: const Text('Item berhasil tersimpan'),
              content: SingleChildScrollView(
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text('Nama: $_name'),
                    Text('Jumlah: $_amount'),
                    Text('Deskripsi: $_description'),
                  ],
                ),
              ),
              actions: [
                TextButton(
                  child: const Text('OK'),
                  onPressed: () {
                    Navigator.pop(context);
                  },
                ),
              ],
            );
          },
        );
        _formKey.currentState!.reset();
      }
    },
    ```

  4. Membuat sebuah drawer pada aplikasi dengan ketentuan sebagai berikut:
    - Drawer minimal memiliki dua buah opsi, yaitu `Halaman Utama` dan `Tambah Item`. Ketika memiih opsi `Halaman Utama`, maka aplikasi akan mengarahkan pengguna ke halaman utama. Ketika memiih opsi `Tambah Item`, maka aplikasi akan mengarahkan pengguna ke halaman form tambah item baru.
      - Buat file `left_drawer.dart` untuk membuat drawer yang ada di kiri halaman.
      ```
      import 'package:flutter/material.dart';
      import 'package:peti_library/screens/menu.dart';
      import 'package:peti_library/screens/shoplist_form.dart';

      class LeftDrawer extends StatelessWidget {
        const LeftDrawer({super.key});

        @override
        Widget build(BuildContext context) {
          return Drawer(
            child: ListView(
              children: [
                const DrawerHeader(
                  decoration: BoxDecoration(
                    color: Colors.indigo,
                  ),
                  child: Column(
                    children: [
                      Text(
                        'Shopping List',
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontSize: 30,
                          fontWeight: FontWeight.bold,
                          color: Colors.white,
                        ),
                      ),
                      Padding(padding: EdgeInsets.all(10)),
                      Text("Catat seluruh keperluan belanjamu di sini!",
                          textAlign: TextAlign.center,
                          style: TextStyle(
                            fontSize: 15,
                            color: Colors.white,
                            fontWeight: FontWeight.normal,
                          )),
                    ],
                  ),
                ),
              ]
            )
          )
        }
      }
      ```

      - Tambahkan kode berikut di class `LeftDrawer`.
      ```
      ListTile(
        leading: const Icon(Icons.home_outlined),
        title: const Text('Halaman Utama'),
        // Bagian redirection ke MyHomePage
        onTap: () {
        },
      ),
      ListTile(
        leading: const Icon(Icons.add_shopping_cart),
        title: const Text('Tambah Item'),
        // Bagian redirection ke ShopFormPage
        onTap: (), {
        }
      )
      ```

      - Tambahkan kode navigator dalam `onTap()` untuk pergi ke `Halaman Utama` yaitu `MyHomePage`.
      ```
      onTap: () {
        Navigator.pushReplacement(
            context,
            MaterialPageRoute(
              builder: (context) => MyHomePage(),
            ));
      },
      ```
      - Tambahkan kode navigator dalam `onTap()` untuk pergi ke halaman form `Tambah Item` yaitu `ShopFormPage`.
      ```
      onTap: () {
        Navigator.pushReplacement(
            context,
            MaterialPageRoute(
              builder: (context) => const ShopFormPage(),
            ));
      },
      ```

</details>

<details open>
<summary>Tugas 7</summary>

# Tugas 7

## Jawaban

### Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?

**Stateless Widget**

- Tidak memiliki state internal yang berubah-ubah. Artinya, tidak ada data atau konfigurasi yang diharapkan untuk berubah setelah widget dibuat.
- Setiap kali informasi yang diteruskan ke dalam widget (melalui konstruktor) berubah, widget tersebut akan dibangun ulang untuk mencerminkan perubahan tersebut.
- Cocok untuk antarmuka pengguna yang sederhana dan statis, di mana tampilan tidak bergantung pada objek yang berubah-ubah dalam waktu. Contohnya adalah ikon atau teks yang tidak pernah berubah setelah widget tersebut ditampilkan.
- Mereka meng-override metode build untuk mendeskripsikan bagaimana UI seharusnya terlihat berdasarkan konfigurasi dan properti yang diberikan.

**Stateful Widget**

- Memiliki state internal yang dapat berubah-ubah. Ini berarti bahwa widget dapat mempertahankan keadaan dan dapat diubah selama widget tersebut digunakan.
- Memungkinkan aplikasi untuk menjadi dinamis dan interaktif karena state widget bisa berubah berdasarkan event atau aksi pengguna.
- Terdiri dari dua kelas: satu kelas StatefulWidget yang menangani penciptaan object state, dan satu kelas State yang menangani state tersebut.
- Cocok untuk bagian UI yang memerlukan interaksi pengguna atau pembaruan data, seperti slider atau checkbox yang statusnya (seperti nilai atau apakah dicentang) dapat berubah berdasarkan interaksi pengguna.

### Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.

- `MaterialApp`: Widget root yang digunakan untuk mengatur tema dan navigasi pada aplikasi. Widget ini menyediakan sejumlah widget dan properti default yang umum digunakan dalam material design.
- `Scaffold`: Menyediakan struktur visual dasar untuk layar di aplikasi material design, seperti appBar, body, floatingActionButton, dan lainnya.
- `AppBar`: Widget yang umumnya digunakan di bagian atas Scaffold untuk menampilkan judul aplikasi, _action_, dan leading widget seperti menu hamburger atau back button.
- `SingleChildScrollView`: Widget scrollable yang digunakan untuk membuat bagian dalam layar dapat di-_scroll_, berguna jika konten yang ditampilkan mungkin melebihi ruang layar.
- `Padding`: Widget yang memberikan padding atau jarak di sekeliling widget child-nya, untuk memberi ruang dan mengatur jarak antar elemen UI.
- `Column`: Widget yang menata children-nya secara vertikal. Ini sering digunakan untuk menampilkan serangkaian widget yang satu di atas yang lain.
- `Text`: Widget yang menampilkan string teks dengan berbagai styling seperti ukuran font, berat font (fontWeight), dan lainnya.
- `InkWell`: Widget yang memberikan efek visual saat disentuh atau diklik. Ini sering digunakan untuk memberi respons interaktif pada sentuhan pengguna.
- `Material`: Widget yang menambahkan efek visual material design seperti tinta yang menyebar pada saat InkWell disentuh.
- `Icon`: Widget yang menampilkan simbol atau ikon dari set yang tersedia di Flutter, seperti yang ditemukan dalam Material Icons atau Cupertino Icons.
- `SnackBar`: Sebuah pesan pop-up sementara yang ditampilkan di bagian bawah layar untuk memberikan feedback kepada pengguna.
- `Center`: Widget yang menengahkan child-nya secara horizontal dan/atau vertikal dalam ruang yang tersedia.
- `Container`: Widget yang digunakan untuk mengatur styling tambahan seperti padding, margin, constraints, dan lainnya untuk child widget yang ada di dalamnya.
- `RunApp`: Fungsi yang mengambil widget yang diberikan dan menjadikannya root dari pohon widget.
- `ShopCard`: Widget kustom yang dari StatelessWidget yang menyediakan representasi visual untuk item toko (ShopItem).
- `MyHomePage`: Widget kustom yang diperluas dari StatelessWidget yang bertindak sebagai halaman utama aplikasi.

### Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)

1. **Membuat sebuah program Flutter baru dengan tema inventory.**
- Jalankan command `flutter create peti_library` untuk _generate_ proyek Flutter. (Context : Saya mengambil tema library sama seperti tugas sebelumnya).
- Pindah ke direktori proyek untuk mulai mengubah konten dari kode dengan `cd peti_library`.

2. **Membuat tiga tombol sederhana dengan ikon dan teks**
- Buat file bernama `menu.dart` dan pindahkan class `MyHomePage` dan `_MyHomePageState`ke dalam file tersebut.
- Tambahkan `import 'package:shopping_list/menu.dart';` pada file `main.dart`.
- Pada `main.dart` ubah `MyHomePage(title: 'Flutter Demo Home Page')` menjadi `MyHomePage()`.
- Pada `menu.dart` :
    - Ubah sifat widget halaman dari stateful menjadi stateless. Lakukan hal ini dengan merubah bagian `({super.key, required this.title})` menjadi `({Key? key}) : super(key: key);`.
    - Tambahkan teks dan card dengan menambahkan barang yang dijual (dalam kasus saya buku) dengan _define_ tipe berikut:
    ```
    class ShopItem {
        final String name;
        final IconData icon;

        ShopItem(this.name, this.icon);
    }
    ```
    - Tambahkan barang-barang yang dijual (nama, harga, dan icon barang) dengan menambahkan kode berikut:
    ```
    final List<ShopItem> items = [
        ShopItem("Lihat Produk", Icons.checklist),
        ShopItem("Tambah Produk", Icons.add_shopping_cart),
        ShopItem("Logout", Icons.logout),
    ];
    ```
    - Kemudian tambahkan kode berikut di dalam Widget Build:
    ```
    @override
    Widget build(BuildContext context) {
        return Scaffold(
        appBar: AppBar(
            title: const Text(
            'Peti Library',
            style: TextStyle(color: Colors.white),
            ),
            backgroundColor: Colors.indigo,
        ),
        body: SingleChildScrollView(
            // Widget wrapper yang dapat discroll
            child: Padding(
            padding: const EdgeInsets.all(10.0), // Set padding dari halaman
            child: Column(
                // Widget untuk menampilkan children secara vertikal
                children: <Widget>[
                const Padding(
                    padding: EdgeInsets.only(top: 10.0, bottom: 10.0),
                    // Widget Text untuk menampilkan tulisan dengan alignment center dan style yang sesuai
                    child: Text(
                    'Books Heaven', // Text yang menandakan toko
                    textAlign: TextAlign.center,
                    style: TextStyle(
                        fontSize: 30,
                        fontWeight: FontWeight.bold,
                    ),
                    ),
                ),
                // Grid layout
                GridView.count(
                    // Container pada card kita.
                    primary: true,
                    padding: const EdgeInsets.all(20),
                    crossAxisSpacing: 10,
                    mainAxisSpacing: 10,
                    crossAxisCount: 3,
                    shrinkWrap: true,
                    children: items.map((ShopItem item) {
                    // Iterasi untuk setiap item
                    return ShopCard(item);
                    }).toList(),
                ),
                ],
              ),
            ),
          ),
        );
    }
    ```

3. **Memunculkan Snackbar**
- Terakhir, tampilkan card dan buat Snackbar dengan membuat widget stateless baru:
```
class ShopCard extends StatelessWidget {
  final ShopItem item;

  const ShopCard(this.item, {super.key}); // Constructor

  @override
  Widget build(BuildContext context) {
    return Material(
      color: item.color,
      child: InkWell(
        // Area responsive terhadap sentuhan
        onTap: () {
          // Memunculkan SnackBar ketika diklik
          ScaffoldMessenger.of(context)
            ..hideCurrentSnackBar()
            ..showSnackBar(SnackBar(
                content: Text("Kamu telah menekan tombol ${item.name}!")));
        },
        child: Container(
          // Container untuk menyimpan Icon dan Text
          padding: const EdgeInsets.all(8),
          child: Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                Icon(
                  item.icon,
                  color: Colors.white,
                  size: 30.0,
                ),
                const Padding(padding: EdgeInsets.all(3)),
                Text(
                  item.name,
                  textAlign: TextAlign.center,
                  style: const TextStyle(color: Colors.white),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}
```
Snackbar akan muncul ketika saya menuliskan potongan kode berikut:
```
child: InkWell(
    onTap: () {
    // Memunculkan SnackBar ketika diklik
    ScaffoldMessenger.of(context)
        ..hideCurrentSnackBar()
        ..showSnackBar(SnackBar(
            content: Text("Kamu telah menekan tombol ${item.name}!")));
    },
    ....
)

```

4. **Bonus : Mengimplementasikan warna-warna yang berbeda untuk setiap tombol (`Lihat Item`, `Tambah Item`, dan `Logout`).**
- Buat parameter baru bernama color:
```
class ShopItem {
  final String name;
  final IconData icon;
  final Color color;

  ShopItem(this.name, this.icon, this.color);
}
```
```
final List<ShopItem> items = [
    ShopItem("Lihat Item", Icons.checklist, Colors.purple),
    ShopItem("Tambah Item", Icons.add_shopping_cart, Colors.amber),
    ShopItem("Logout", Icons.logout, Colors.red),
];
```
- Ubah warna pada Widget Build menjadi warna yang telah di-assign pada masing-masing button.
```
class ShopCard extends StatelessWidget {
  final ShopItem item;

  const ShopCard(this.item, {super.key}); // Constructor

  @override
  Widget build(BuildContext context) {
    return Material(
      color: item.color,
      ...
    )
  }
}
```
</details>