import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      initialRoute: '/', // Halaman awal
      routes: {
        '/': (context) => SplashPage(),
        '/menu': (context) => MenuPage(),
        '/login': (context) => LoginPage(),
        '/register': (context) => RegisterPage(),
      },
    );
  }
}

class SplashPage extends StatelessWidget {
  const SplashPage({super.key});

  @override
  Widget build(BuildContext context) {
    double screenHeight = MediaQuery.of(context).size.height;
    double screenWidth = MediaQuery.of(context).size.width;
    return Scaffold(
      body: Stack(
        children: [
          // Background image (Gambar1)
          Container(
            width: double.infinity,
            height: double.infinity, // Menambahkan tinggi penuh layar
            decoration: const BoxDecoration(
              image: DecorationImage(
                image: AssetImage(
                    'images/Gambar1.png'), // Gambar background pegunungan
                fit: BoxFit
                    .fill, // Mengubah dari cover menjadi contain agar gambar tidak terpotong
              ),
            ),
          ),
          // Gambar yang bertumpuk di bagian bawah (Gambar6 hingga Gambar13)
          Positioned(
            bottom: -100, // Memastikan gambar berada di bagian bawah layar
            left: 0,
            right: 0,
            child: Stack(
              children: [
                Image.asset(
                  'images/Gambar6.png',
                  width: double.infinity,
                  height: MediaQuery.of(context).size.height *
                      0.2, // Sesuaikan tinggi gambar
                  fit: BoxFit
                      .fill, // Menggunakan contain agar gambar tidak terpotong
                ),
                Positioned.fill(
                  child: Image.asset(
                    'images/Gambar8.png',
                    width: double.infinity,
                    height: MediaQuery.of(context).size.height * 0.2,
                    fit: BoxFit.fill, // Menjaga gambar tidak terpotong
                  ),
                ),
                Positioned.fill(
                  child: Image.asset(
                    'images/Gambar10.png',
                    width: double.infinity,
                    height: MediaQuery.of(context).size.height * 0.2,
                    fit: BoxFit.fill,
                  ),
                ),
                Positioned.fill(
                  child: Image.asset(
                    'images/Gambar12.png',
                    width: double.infinity,
                    height: MediaQuery.of(context).size.height * 0.2,
                    fit: BoxFit.fill,
                  ),
                ),
                Positioned.fill(
                  child: Image.asset(
                    'images/Gambar13.png',
                    width: double.infinity,
                    height: MediaQuery.of(context).size.height * 0.2,
                    fit: BoxFit.fill,
                  ),
                ),
              ],
            ),
          ),
          // Logo Aqua (Gambar2) dan teks diposisikan menggunakan Positioned
          Positioned(
            top: 0, // Posisi vertikal dari atas
            left: 0,
            right: 0,
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                Image.asset(
                  'images/Gambar2.png', // Gambar logo Aqua
                  height: 200,
                ),
                const SizedBox(height: 0),
                const Text(
                  'KEBAIKAN\nBERAWAL\nDARI SINI',
                  textAlign: TextAlign.center,
                  style: TextStyle(
                    fontSize: 28,
                    color: Colors.white,
                    fontWeight: FontWeight.bold,
                  ),
                ),
                const SizedBox(height: 10),
                const Text(
                  'Terpercaya lebih\ndari 45 tahun',
                  textAlign: TextAlign.center,
                  style: TextStyle(
                    fontSize: 16,
                    color: Colors.white,
                  ),
                ),
              ],
            ),
          ),
          // Tombol panah di bawah teks dan di atas botol
          Positioned(
            bottom: screenHeight * 0.25, // Posisi tombol dari bawah layar
            left: (screenWidth - 60) / 2, // Mengatur tombol di tengah
            child: ElevatedButton(
              onPressed: () {
                Navigator.pushNamed(context, '/menu');
              },
              style: ElevatedButton.styleFrom(
                shape: const CircleBorder(),
                padding: const EdgeInsets.all(20),
                backgroundColor: Colors.white,
              ),
              child: const Icon(
                Icons.arrow_forward,
                color: Color.fromARGB(255, 69, 115, 222),
              ),
            ),
          ),
          // Botol Aqua positioned di bagian bawah layar
          Positioned(
            bottom: 0,
            left: 0,
            right: 0,
            child: Image.asset(
              'images/Gambar4.png',
              height: MediaQuery.of(context).size.height * 0.3,
              fit: BoxFit.contain,
            ),
          ),
        ],
      ),
    );
  }
}

// Halaman kedua (Menu Login/Register)
class MenuPage extends StatelessWidget {
  const MenuPage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Image.asset('images/Gambar2.png', height: 200),
            const SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                Navigator.pushNamed(context, '/login');
              },
              style: ElevatedButton.styleFrom(
                iconColor: Colors.white,
                backgroundColor: const Color.fromARGB(255, 69, 115, 222),
                minimumSize: const Size(double.infinity, 50),
              ),
              child: Text('Login'),
            ),
            const SizedBox(height: 20),
            OutlinedButton(
              onPressed: () {
                Navigator.pushNamed(context, '/register');
              },
              style: OutlinedButton.styleFrom(
                side:
                    const BorderSide(color: Color.fromARGB(255, 69, 115, 222)),
                minimumSize: const Size(double.infinity, 50),
              ),
              child: Text('Register'),
            ),
            const SizedBox(height: 10),
            const Text(
              'Kebaikan Alam\nKebaikan Hidup',
              textAlign: TextAlign.center,
              style: TextStyle(fontSize: 18, color: Colors.black),
            ),
          ],
        ),
      ),
    );
  }
}

// Halaman ketiga (Login Page)
class LoginPage extends StatefulWidget {
  const LoginPage({super.key});

  @override
  _LoginPageState createState() => _LoginPageState();
}

class _LoginPageState extends State<LoginPage> {
  bool _isObscured = true;
  IconData _iconVisible = Icons.visibility_off;

  void _togglePasswordView() {
    setState(() {
      _isObscured = !_isObscured;
      _iconVisible = _isObscured ? Icons.visibility_off : Icons.visibility;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.white,
        elevation: 0,
        leading: IconButton(
          icon: const Icon(Icons.arrow_back, color: Colors.black),
          onPressed: () => Navigator.pop(context),
        ),
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            const TextField(
              decoration: InputDecoration(
                labelText: 'Email',
                prefixIcon: Icon(Icons.email),
                border: OutlineInputBorder(),
              ),
            ),
            const SizedBox(height: 20),
            TextField(
              decoration: InputDecoration(
                labelText: 'Kata Sandi',
                prefixIcon: const Icon(Icons.lock),
                suffixIcon: IconButton(
                  icon: Icon(_iconVisible),
                  onPressed: _togglePasswordView,
                ),
                border: const OutlineInputBorder(),
              ),
              obscureText: _isObscured,
            ),
            const SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                // Aksi login
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: const Color.fromARGB(255, 69, 115, 222),
                minimumSize: const Size(double.infinity, 50),
              ),
              child: Text('Login'),
            ),
          ],
        ),
      ),
    );
  }
}

// Halaman keempat (Register Page)
class RegisterPage extends StatefulWidget {
  const RegisterPage({super.key});

  @override
  _RegisterPageState createState() => _RegisterPageState();
}

class _RegisterPageState extends State<RegisterPage> {
  bool _isObscured1 = true; // Kata sandi
  bool _isObscured2 = true; // Konfirmasi kata sandi

  void _togglePasswordView1() {
    setState(() {
      _isObscured1 = !_isObscured1;
    });
  }

  void _togglePasswordView2() {
    setState(() {
      _isObscured2 = !_isObscured2;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.white,
        elevation: 0,
        leading: IconButton(
          icon: const Icon(Icons.arrow_back, color: Colors.black),
          onPressed: () => Navigator.pop(context),
        ),
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            const TextField(
              decoration: InputDecoration(
                labelText: 'Nama Lengkap',
                prefixIcon: Icon(Icons.person),
                border: OutlineInputBorder(),
              ),
            ),
            const SizedBox(height: 20),
            const TextField(
              decoration: InputDecoration(
                labelText: 'Email',
                prefixIcon: Icon(Icons.email),
                border: OutlineInputBorder(),
              ),
            ),
            const SizedBox(height: 20),
            TextField(
              decoration: InputDecoration(
                labelText: 'Kata Sandi',
                prefixIcon: const Icon(Icons.lock),
                suffixIcon: IconButton(
                  icon: Icon(
                      _isObscured1 ? Icons.visibility_off : Icons.visibility),
                  onPressed: _togglePasswordView1,
                ),
                border: const OutlineInputBorder(),
              ),
              obscureText: _isObscured1,
            ),
            const SizedBox(height: 20),
            TextField(
              decoration: InputDecoration(
                labelText: 'Konfirmasi Kata Sandi',
                prefixIcon: const Icon(Icons.lock),
                suffixIcon: IconButton(
                  icon: Icon(
                      _isObscured2 ? Icons.visibility_off : Icons.visibility),
                  onPressed: _togglePasswordView2,
                ),
                border: const OutlineInputBorder(),
              ),
              obscureText: _isObscured2,
            ),
            const SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                // Aksi register
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: const Color.fromARGB(255, 69, 115, 222),
                minimumSize: const Size(double.infinity, 50),
              ),
              child: Text('Register'),
            ),
          ],
        ),
      ),
    );
  }
}
