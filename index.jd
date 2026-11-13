const { Client, LocalAuth } = require('whatsapp-web.js');
const qrcode = require('qrcode-terminal');

const client = new Client({
    authStrategy: new LocalAuth(),
    puppeteer: { 
        headless: true,
        args: ['--no-sandbox', '--disable-setuid-sandbox', '--disable-gpu'] 
    }
});

const CHANNEL_ID = '0029VbDqsVe59PwYb3g5hP3K@newsletter';
const NOMOR_KAU = '6283178162622'; 

client.on('qr', (qr) => {
    console.log('SCAN QR INI CIO!');
    qrcode.generate(qr, { small: true });
});

client.on('ready', async () => {
    console.log('BOT ARX SQUAD UDAH IDUP 24 JAM!');
    try {
        await client.sendMessage(CHANNEL_ID, `⚡🔥 *ARX SQUAD BOT ONLINE!* 🔥⚡\n\nBot 24 Jam Udah Idup!\nHP Admin Boleh Mati, Bot Tetep Jalan!`);
        console.log('TEST BERHASIL KEPOST!');
    } catch (e) {
        console.log('Gagal posting: ' + e);
    }
});

client.initialize().then(async () => {
    setTimeout(async () => {
        try {
            const code = await client.requestPairingCode(NOMOR_KAU);
            console.log('KODE PAIRING KAU: ' + code);
            console.log('MASUKIN KODE INI DI WA KAU!');
        } catch(e) { console.log('Gagal minta kode: ' + e); }
    }, 5000);
});

setInterval(() => { console.log('Bot masih idup...'); }, 60000);
