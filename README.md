# Lybaz Billing System

**Sistem Billing ISP Modern** untuk mengelola pelanggan internet dengan integrasi lengkap: FreeRADIUS, Payment Gateway, dan WhatsApp Gateway.

---

## Mengapa Lybaz Billing?

| Kebutuhan | Solusi |
|-----------|--------|
| Pelanggan lupa bayar | Reminder otomatis via WhatsApp 3 hari sebelum jatuh tempo |
| Proses perpanjangan manual | Auto-renewal otomatis jika saldo cukup |
| Tagihan sulit dibayar | Link pembayaran langsung ke QRIS/VA/E-Wallet |
| Staff tidak bisa dipantau | Revenue tracking per operator |
| Setup ribet | Deploy 1 command, scheduler otomatis |

---

## Fitur Utama

### 💳 Payment Gateway (Midtrans)
- QRIS - Semua e-wallet (0.7%)
- Virtual Account - BCA, BNI, BRI, Mandiri, Permata
- E-Wallet - GoPay, ShopeePay
- Pembayaran otomatis tercatat di sistem

### 💬 WhatsApp Gateway
- Multi-device support
- Broadcast ke banyak pelanggan sekaligus
- Template pesan dengan variable otomatis (nama, tagihan, link bayar)
- Reminder otomatis 3 hari sebelum jatuh tempo
- Notifikasi pembayaran berhasil

### 📶 Integrasi FreeRADIUS
- PPPoE, Hotspot, DHCP
- Bandwidth control otomatis
- Disconnect otomatis saat expired
- Multi-NAS (banyak router)
- Real-time session monitoring

### 📊 Manajemen Pelanggan
- Dashboard pelanggan lengkap
- Riwayat pembayaran
- Riwayat langganan
- Top-up saldo online
- Portal self-service

### 💰 Revenue & Settlement
- Dashboard revenue real-time
- Tracking revenue per operator/staff
- Kategorisasi: Top-Up, Langganan, Renewal, Voucher
- Approval settlement

### 🔄 Auto-Renewal
- Perpanjangan otomatis jika saldo cukup
- Threshold adaptif (sesuai durasi paket)
- Fair bonus untuk penggunaan tidak terpakai
- Zero-downtime (tidak ada putus koneksi)

---

## Teknologi

| Komponen | Stack |
|----------|-------|
| Backend | Laravel 12, PHP 8.4 |
| Frontend | Livewire 3, Tailwind CSS |
| Database | MySQL |
| WhatsApp | Node.js, whatsapp-web.js |
| Payment | Midtrans |
| Auth | FreeRADIUS |
| Tunnel | Cloudflare (opsional) |

---

## Deployment

```bash
# Deploy lengkap (1 command)
./deploy.sh deploy

# Sudah termasuk:
# - Database backup
# - Code update
# - Migration
# - Scheduler setup
# - Service restart
```

---

## Scheduler Otomatis

| Task | Jadwal |
|------|--------|
| Reminder tagihan (3 hari) | 08:00 |
| Reminder langganan expire | 09:00 |
| Notifikasi expired | 10:00 |
| Reminder tagihan (hari H) | 11:00 |
| Auto-renewal paket | Setiap 1-15 menit |
| Backup database | 02:00 |

---

## Paket Langganan Didukung

- **PPPoE** - Fiber/dedicated
- **Hotspot** - Voucher/unlimited
- **DHCP** - IP binding
- **Fixed Date** - Tagihan tanggal tetap

---

## Template WhatsApp

| Template | Kegunaan |
|----------|----------|
| Payment Reminder | Tagihan akan jatuh tempo |
| Subscription Expiring | Langganan akan habis |
| Subscription Expired | Langganan sudah habis |
| Payment Confirmation | Pembayaran berhasil |
| Welcome Customer | Pelanggan baru |
| Balance Added | Top-up saldo berhasil |

Semua template mengisi data otomatis: nama pelanggan, jumlah tagihan, tanggal, link pembayaran.

---

## Kebutuhan Server

| Spesifikasi | Minimum | Rekomendasi |
|-------------|---------|-------------|
| RAM | 2GB | 4GB |
| Storage | 20GB | 50GB |
| CPU | 2 core | 4 core |
| OS | Ubuntu 22.04 / Debian 12 | Ubuntu 24.04 |

Mendukung ARM (Orange Pi, Raspberry Pi).

---

## Lisensi

Proprietary - Hubungi untuk informasi lisensi.

---

## Kontak

- **Website**: [lybaz.net](https://lybaz.net)
- **Dokumentasi**: [docs.lybaz.net](https://docs.lybaz.net)

---

*Lybaz Billing System v2.3 - Desember 2025*
