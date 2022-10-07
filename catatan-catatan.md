- J**ika ingin membuat lebar image sama dengan lebar layarnya : **
  > width:MediaQuery.of(context).size.width

* **Navigator.pop(context) =digunakan untuk membuat fungsi button back ke halaman sebelumnya**

* **Memberikan border radius pada container bagian atas**

  > decoration:BoxDecoration(borderRadius:BorderRadius.vertical(
  > top:Rdius.circular(20),
  > ))

* **Memberikan border radius pada image :**

  > ClipRRect(
  > borderRadius: BorderRadius.circular(8.0),
  > child: Image.network(
  > subject['images']['large'],
  > height: 150.0,
  > width: 100.0,
  > ),
  > )

* **Memberikan border radius pada Container :**

> decoration: BoxDecoration(
> borderRadius: BorderRadius.circular(10),

- **Memberikan color pada ElevatedButton :**
  > child: ElevatedButton(
  > child: Text('Pesan Sekarang'),
  > onPressed: () {},
  > style: ElevatedButton.styleFrom(backgroundColor: redColor,)

* **Memberikan border radius pada ElevatedButton :**

  > shape: RoundedRectangleBorder(
  > borderRadius: BorderRadius.circular(10),

* **Membuat route kembali ke halaman tertentu**

  > onPressed: () {
  > Navigator.pushAndRemoveUntil(
  > context,
  > MaterialPageRoute(builder: (context) => HomePage()),
  > (route) => false);
  > },

* **Membuat background image**

> body: Stack(
> children: [
>
> > Container(
> > width: double.infinity,
> > height: double.infinity,
> > decoration: BoxDecoration(
> > image: DecorationImage(image: AssetImage('assets/plane.jpg'))),
> > )
> > ],
> > ),

- **Membuat perpindahan dari splash_page ke get_started_page secara otomatis**

> @override
> void initState() {
> // TODO: implement setState
> Timer(Duration(seconds: 3), () {
> Navigator.push(
> context, MaterialPageRoute(builder: (context) => GetStarted()));
> });
> super.initState();
> }

atau dapat juga dengan menggunakan _pushNamed_

1.  Pada main.dart buat routes untuk menggantikan home nya

> routes: {
> '/': (context) => SplashPage(),
> '/get-started': (context) => GetStarted(),
> },

2.  Ubah code _Navigator_ nya menjadi :
    > @override
    > void initState() {
    > // TODO: implement setState
    > Timer(Duration(seconds: 3), () {
    >
    >      Navigator.pushNamed(context, '/get-started');
    >
    > });
    > super.initState();
    > }
