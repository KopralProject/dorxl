# 🤖 DOR Bot - WhatsApp Bot for XL DOR Service

[![Node.js Version](https://img.shields.io/badge/node-%3E%3D14.0.0-brightgreen)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![PM2](https://img.shields.io/badge/PM2-Process%20Manager-green)](https://pm2.keymetrics.io/)

A powerful WhatsApp bot built with Node.js for handling XL DOR (Data Override) service requests, featuring OTP verification and seamless payment processing.

## ✨ Features

- 🔐 **Secure OTP Authentication**
  - 5-minute validity period
  - 3 maximum validation attempts
  - Automatic session management

- 💳 **QRIS Payment Integration**
  - Real-time payment status monitoring
  - 5-minute payment timeout
  - Automatic payment verification

- 📱 **User-Friendly Interface**
  - Simple command-based interaction
  - Clear payment instructions
  - QR code generation

- 📊 **Advanced Logging**
  - Multi-level logging system
  - Colored console output
  - File-based logging
  - Detailed error tracking

## 🚀 Quick Start

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- WhatsApp account for bot
- API keys for:
  - DOR Service API
  - Tripay Payment Gateway
  - OrderKuota Payment Gateway (bebas mau pake ini atau tripay)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/AutoFTbot/DorXLHORE.git
cd DorXLHORE 
```

2. Install dependencies:
```bash
npm install
```

### Configuration

Update the following configuration in `dor/app.js`:

```javascript
const DOR_CONFIG = {
    apiUrl: 'YOUR_DOR_API_URL',
    apiKey: 'YOUR_DOR_API_KEY',
    price: 10000 // Customize based on your needs
}

const TRIPAY_CONFIG = {
    apiKey: "YOUR_TRIPAY_API_KEY",
    privateKey: "YOUR_TRIPAY_PRIVATE_KEY",
    merchantCode: "YOUR_MERCHANT_CODE"
}
```

## 🛠️ Running the Bot

### Using Node.js (Development)

```bash
node dor/app.js
```

### Using PM2 (Production)

1. Install PM2 globally:
```bash
npm install -g pm2
```

2. Start the bot as a service:
```bash
pm2 start dor/app.js --name "dor-bot"
```

3. Common PM2 commands:
```bash
# View logs
pm2 logs dor-bot

# Monitor the bot
pm2 monit

# Restart the bot
pm2 restart dor-bot

# Stop the bot
pm2 stop dor-bot

# Delete the bot from PM2
pm2 delete dor-bot
```

4. Configure PM2 to start on system boot:
```bash
pm2 startup
pm2 save
```

## 📝 Available Commands

- `.mintaotp <nomor_hp>` - Request OTP
- `.verifotp <kode_otp>` - Verify OTP
- `.dor` - Start DOR process
- `.lanjutdor` - Continue with payment
- `.dors` - Show menu

## 🔒 Security Features

- Secure API key storage
- Session-based authentication
- Automatic token expiration
- Input validation
- Error handling and logging

## 📁 Project Structure

```
DorXLHORE/
├── dor/
│   ├── app.js            # Main bot implementation
│   ├── bot.log           # Log file
│   ├── otp_data.json     # OTP data storage
│   └── orderkuota.js     # OrderKuota payment integration
└── README.md             # Documentation
```

## 📦 Dependencies

- [@mengkodingan/ckptw](https://github.com/mengkodingan/ckptw) - WhatsApp client
- [axios](https://github.com/axios/axios) - HTTP client
- [qrcode](https://github.com/soldair/node-qrcode) - QR code generation
- [crypto](https://nodejs.org/api/crypto.html) - Cryptographic functions
- [fs](https://nodejs.org/api/fs.html) - File system operations

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 💬 Support

For support, please:
- Open an issue in the GitHub repository
- Contact the maintainer
- Join our [Telegram Group](https://t.me/fightertunnell)

## 🙏 Acknowledgments

- [RizkyHdyt](https://t.me/rizkihdyt) - Service provider Api & Akses
- [@mengkodingan/ckptw](https://github.com/mengkodingan/ckptw) - WhatsApp client library
- [Tripay](https://tripay.co.id) - Payment gateway
- [XL](https://www.xl.co.id) - Service provider 
