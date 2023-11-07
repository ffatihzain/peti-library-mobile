# Muhammad Fatih Zain

## PBP A - 2206824073


<details open>
<summary>Tugas 7</summary>

# Tugas 7

## Jawaban

### Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?

**Stateless Widge**

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

`MaterialApp`: Widget root yang digunakan untuk mengatur tema dan navigasi pada aplikasi. Widget ini menyediakan sejumlah widget dan properti default yang umum digunakan dalam material design.
`Scaffold`: Menyediakan struktur visual dasar untuk layar di aplikasi material design, seperti appBar, body, floatingActionButton, dan lainnya.
`AppBar`: Widget yang umumnya digunakan di bagian atas Scaffold untuk menampilkan judul aplikasi, _action_, dan leading widget seperti menu hamburger atau back button.
`SingleChildScrollView`: Widget scrollable yang digunakan untuk membuat bagian dalam layar dapat di-_scroll_, berguna jika konten yang ditampilkan mungkin melebihi ruang layar.
`Padding`: Widget yang memberikan padding atau jarak di sekeliling widget child-nya, untuk memberi ruang dan mengatur jarak antar elemen UI.
`Column`: Widget yang menata children-nya secara vertikal. Ini sering digunakan untuk menampilkan serangkaian widget yang satu di atas yang lain.
`Text`: Widget yang menampilkan string teks dengan berbagai styling seperti ukuran font, berat font (fontWeight), dan lainnya.
`InkWell`: Widget yang memberikan efek visual saat disentuh atau diklik. Ini sering digunakan untuk memberi respons interaktif pada sentuhan pengguna.
`Material`: Widget yang menambahkan efek visual material design seperti tinta yang menyebar pada saat InkWell disentuh.
`Icon`: Widget yang menampilkan simbol atau ikon dari set yang tersedia di Flutter, seperti yang ditemukan dalam Material Icons atau Cupertino Icons.
`SnackBar`: Sebuah pesan pop-up sementara yang ditampilkan di bagian bawah layar untuk memberikan feedback kepada pengguna.
`Center`: Widget yang menengahkan child-nya secara horizontal dan/atau vertikal dalam ruang yang tersedia.
`Container`: Widget yang digunakan untuk mengatur styling tambahan seperti padding, margin, constraints, dan lainnya untuk child widget yang ada di dalamnya.
`RunApp`: Fungsi yang mengambil widget yang diberikan dan menjadikannya root dari pohon widget.
`ShopCard`: Widget kustom yang dari StatelessWidget yang menyediakan representasi visual untuk item toko (ShopItem).
`MyHomePage`: Widget kustom yang diperluas dari StatelessWidget yang bertindak sebagai halaman utama aplikasi.

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