Berikut adalah **roadmap belajar dan membangun proyek Modular Smart Wallet berbasis ERC-4337** (Account Abstraction) untuk level intermediate–advanced Web3 developer seperti kamu.

---

## 🗺️ Roadmap: **Smart Wallet dengan Account Abstraction (ERC-4337)**

---

### ✅ **Phase 1 — Foundation (Week 1)**

> **Goal:** Pahami dasar Account Abstraction dan ekosistem ERC-4337.

#### 📚 Belajar Teori

* [ ] Pahami **Account Abstraction (AA)**: konsep dan motivasinya

  * [Ethereum Blog: AA](https://blog.ethereum.org/2021/12/06/account-abstraction)
* [ ] Pelajari spesifikasi **ERC-4337**:

  * [ERC-4337 Official Spec](https://eips.ethereum.org/EIPS/eip-4337)
* [ ] Pelajari elemen penting: `UserOperation`, `Bundler`, `EntryPoint`, `Paymaster`, `SmartAccount`.

#### 🔧 Praktik Dasar

* [ ] Deploy kontrak dummy `EntryPoint.sol` (dari repo ERC-4337)
* [ ] Uji `UserOperation` dengan bundler lokal atau testnet bundler dari:

  * [Stackup](https://docs.stackup.sh/docs)
  * [Alchemy AA](https://docs.alchemy.com/docs/account-abstraction)

---

### 🛠️ **Phase 2 — Smart Wallet Core (Week 2–3)**

> **Goal:** Membangun smart contract wallet dasar + integrasi ke frontend.

#### 📦 Kontrak `SmartWallet.sol`

* [ ] Fungsi `executeCall()` untuk memanggil kontrak lain
* [ ] Fungsi `validateUserOp()` agar kompatibel dengan ERC-4337
* [ ] Signature checking dan nonce tracking
* [ ] Modular structure untuk penambahan plugin ke depan

#### 🧪 Testing

* [ ] Unit test pakai **Foundry**
* [ ] Gunakan `cheatcodes` untuk testing signature, nonce, call forwarding

#### 💻 Frontend (Next.js + Wagmi + Viem)

* [ ] Wallet creation (deploy SmartWallet contract)
* [ ] Call `execute()` untuk transaksi seperti transfer ETH/ERC20
* [ ] Tampilkan status transaksi dari bundler

---

### 🔐 **Phase 3 — Gas Abstraction + Sponsorship (Week 4)**

> **Goal:** Buat transaksi tanpa harus punya ETH (gasless tx).

#### 🔧 Kontrak `Paymaster.sol`

* [ ] Validasi signature transaksi yang disponsori
* [ ] Logika refund dan limit sponsor

#### 🌐 Backend Sponsorship API

* [ ] Daftarkan user dan berikan `sponsored gas`
* [ ] Validasi user yang eligible pakai JWT/email

#### Frontend

* [ ] Toggle untuk "Use Sponsor"
* [ ] Tampilkan estimasi gas dan pilihan metode bayar gas (ETH vs sponsor)

---

### 🧠 **Phase 4 — Social Recovery & Guardian (Week 5)**

> **Goal:** Menyediakan mekanisme pemulihan wallet jika pemilik kehilangan akses.

#### Kontrak Recovery Logic

* [ ] Tambahkan array `guardians`
* [ ] Fungsi `initiateRecovery()` → perlu disetujui oleh mayoritas guardian
* [ ] Fungsi `finalizeRecovery()` setelah delay N hari

#### Frontend

* [ ] UI untuk menambah/menghapus guardian
* [ ] UI untuk inisiasi dan approval recovery

---

### 🎯 **Phase 5 — Fitur Lanjutan (Week 6–7)**

> Fitur ini opsional tapi bisa sangat powerful untuk showcase skill kamu.

* [ ] **Batched Transactions** (eksekusi banyak transaksi sekaligus)
* [ ] **Whitelist Plugin System** untuk membatasi kontrak yang bisa diakses
* [ ] **Gas Payment with ERC20** (stablecoin, misalnya USDC)
* [ ] **Deploy di Layer 2** seperti Base, Arbitrum, atau zkSync

---

## 🎁 Bonus Tools & SDKs

| Tool                                        | Kegunaan                        |
| ------------------------------------------- | ------------------------------- |
| [Zerodev](https://docs.zerodev.app/)        | SDK Account Abstraction         |
| [Biconomy SDK](https://docs.biconomy.io/)   | Plug-and-play Smart Account     |
| [Stackup Bundler](https://docs.stackup.sh/) | Public bundler                  |
| [Alchemy AA SDK](https://docs.alchemy.com/) | SDK ERC-4337                    |
| [Safe Core](https://docs.safe.global/)      | Smart contract wallet + plugins |

---

## 🎓 Hasil Akhir (Goal Capstone)

Build kamu akan menjadi:

* Smart wallet dengan batched tx, sponsor gas, dan social recovery
* Bisa dijadikan dasar wallet SDK atau digunakan dalam dApp milikmu
* Showcase untuk portofolio profesional Web3 developer

---

Kalau kamu ingin, saya bisa bantu:

* Buatkan boilerplate project
* Setup bundler + paymaster
* Refactor smart wallet ke modular pattern
* Tambahkan fitur step by step

Apakah kamu ingin mulai dari kontrak smart wallet-nya dulu atau setup bundler/paymaster?
