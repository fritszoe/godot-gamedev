# Latihan: Playtest

- Apa saja pesan log yang dicetak pada panel Output?:
    - --   
    Reached Objective 
- Coba gerakkan landasan ke batas area bawah, lalu gerakkan kembali ke atas hingga hampir menyentuh batas atas. Apa saja pesan log yang dicetak pada panel Output?
    - --
    Reached Objective

- Buka scene MainLevel dengan tampilan workspace 2D. Apakah lokasi scene ObjectiveArea memiliki kaitan dengan pesan log yang dicetak pada panel Output pada percobaan sebelumnya?
    - --
    Ya, karena berdasarkan script yang diberikan kepada ObjectiveArea, apabila BlueShip enter ObjectiveArea dimana ObjectiveArea adalah sebuah Area2D, ObjectiveArea akan mencetak **"Reached Objective"**
    ```gd
    extends Area2D

    func _on_ObjectiveArea_body_entered(body: RigidBody2D):
	    if (body.name == "BlueShip"):
		    print("Reached objective!")
    ```

# Latihan: Memanipulasi Node & Scene

- Scene BlueShip dan StonePlatform sama-sama memiliki sebuah child node bertipe Sprite. Apa fungsi dari node bertipe Sprite?
    - --
    Sprite node adalah node yang berfungsi untuk menampilkan 2D texture dimana texture disini berupa **.png** atau **.jpg**

- Root node dari scene BlueShip dan StonePlatform menggunakan tipe yang berbeda. BlueShip menggunakan tipe RigidBody2D, sedangkan StonePlatform menggunakan tipe StaticBody2D. Apa perbedaan dari masing-masing tipe node?
    - --
    RigidBody2D dapat dimanipulasi hal-hal seperti massa, inersia, gaya yang berlaku, pokoknya hukum-hukum fisika sedangkan StaticBody2D tidak bisa
    
- Ubah nilai atribut Mass pada tipe RigidBody2D secara bebas di scene BlueShip, lalu coba jalankan scene MainLevel. Apa yang terjadi?
    - --
    Mass diubah menjadi 300Kg dan ship tidak melompat dari platform, dan saat platform di drop jatuhnya sangat cepat

- Ubah nilai atribut Disabled pada tipe CollisionShape2D di scene StonePlatform, lalu coba jalankan scene MainLevel. Apa yang terjadi?
    - --
    Ship terjatuh karena CollisionShape2D nya di Disabled sehingga tidak ada collision antar object 2D

- Pada scene MainLevel, coba manipulasi atribut Position, Rotation, dan Scale milik node BlueShip secara bebas. Apa yang terjadi pada visualisasi BlueShip di Viewport?
    - --
    Posisi, scale, dan arah menghadap BlueShip berubah

- Pada scene MainLevel, perhatikan nilai atribut Position node PlatformBlue, StonePlatform, dan StonePlatform2. Mengapa nilai Position node StonePlatform dan StonePlatform2 tidak sesuai dengan posisinya di dalam scene (menurut Inspector) namun visualisasinya berada di posisi yang tepat?
    - --
    Karena mereka merupakan child node dari PlatformBlue, jadi position nya ke override oleh parent nya

# Level 2

- Added push logic
- Added loops to levels, level 1 -> level 2 -> level 1 -> level 2, karena masih 2 level saja