# 🏆 Act of Valor
📋 Gambaran Challenge
**Difficulty Level:** `Easy` **Topic:** Control Flow - Switch Statements **Language:** JavaScript

🎯 Tujuan
Buat sebuah function yang menentukan apakah suatu action tertentu memenuhi syarat sebagai "act of valor" menggunakan switch statement untuk mengevaluasi berbagai scenario.

📝 Deskripsi Masalah
Anda perlu mengimplementasikan function bernama `actOfValor` yang:
* **Menerima:** Parameter `string` yang merepresentasikan sebuah action
* **Menggunakan:** Switch statement untuk decision making
* **Mengembalikan:** Message spesifik berdasarkan tipe action

✅ Requirements
Function Specification

```javascript
function actOfValor(action) {
    // Your implementation here
}
```

Decision Logic
Function tersebut harus mengevaluasi actions menggunakan switch statement:

Acts of Valor ⚔️
Return: `"This is an act of valor!"`
* `"save a life"`
* `"help the elderly"`
* `"defend the weak"`

Other Actions 🚫
Return: `"This action is not considered an act of valor."`
* Action apapun yang tidak terdaftar di atas

💡 Implementation Hints
1. Gunakan switch statement sebagai control structure utama
2. Pertimbangkan untuk menggunakan case statements untuk setiap valorous action
3. Sertakan default case untuk non-valorous actions
4. Ingat untuk menggunakan break statements untuk mencegah fall-through

🔍 Contoh Penggunaan

```javascript
// Expected outputs
actOfValor("save a life");     // "This is an act of valor!"
actOfValor("help the elderly"); // "This is an act of valor!"
actOfValor("defend the weak");  // "This is an act of valor!"
actOfValor("eat pizza");       // "This action is not considered an act of valor."
```

🎨 Code Structure Template

```javascript
function actOfValor(action) {
    switch (action) {
        // Add your cases here
        
        default:
            // Default case logic
    }
}
```

🏅 Kriteria Sukses
* ✅ Function menggunakan switch statement
* ✅ Mengidentifikasi ketiga acts of valor dengan benar
* ✅ Mengembalikan messages yang tepat untuk kedua scenario
* ✅ Menangani input string apapun dengan proper
* ✅ Code bersih dan readable

**Good luck dengan implementation Anda! 🚀**
