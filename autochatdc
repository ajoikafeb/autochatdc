import time  # Untuk Timer
import requests  # Untuk Ngambil Data Chat
import random  # Untuk Ngambil Message Dari Table Array

headers = {
    'Host': 'discord.com',
    'User -Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:137.0) Gecko/20100101 Firefox/137.0',
    'Accept': '*/*',
    'Accept-Language': 'id,en-US;q=0.7,en;q=0.3',
    'Content-Type': 'application/json',
    'Authorization': '',  # Authorization Code Ambil Di Browser
    'X-Super-Properties': '',  # Ganti pake super properties ambil dari browser
    'X-Discord-Locale': 'en-US',
    'X-Discord-Timezone': 'Asia/Jakarta',
    'X-Debug-Options': 'bugReporterEnabled',
    'Origin': 'https://discord.com',
    'Connection': 'keep-alive',
    'Referer': 'https://discord.com/channels/1146280066947485769/1338425475269263400',
    'Cookie': '',
    'Sec-Fetch-Dest': 'empty',
}

def deleteMessage(message_id):
    urlDelete = f"https://discord.com/api/v9/channels/1338425475269263400/messages/{message_id}"  # 1357333026836582551 ID Channel
    res = requests.delete(urlDelete, headers=headers)
    
    if res.status_code == 204:
        print("[+] pesan berhasil dihapus:", message_id)
    else:
        print("[x] gagal menghapus pesan:", message_id)

def sendMessage(text):
    data = {
        "content": text,
        "nonce": str(int(time.time())),
        "tts": False
    }
    urlMessage = "https://discord.com/api/v9/channels/1338425475269263400/messages"  # 1357333026836582551 ID Channel
    try:
        res = requests.post(urlMessage, json=data, headers=headers)
        #print("Status Code:", res.status_code) #Hapus # Untuk Cek status
        #print("Response:", res.text) #Hapus # Untuk Cek status
        
        if res.status_code == 200:
            message_id = res.json().get("id")  # Ambil ID pesan dari respons
            print("[+] pesan berhasil dikirim:", text)
            return message_id
        else:
            print("[x] pesan gagal dikirim:", text)
            return None
    except requests.exceptions.RequestException as e:
        print("[x] Terjadi kesalahan saat mengirim pesan:", e)

def main():
    messages = [
        "Selamat Pagi Badut",
        "Halo Badut, semoga harimu menyenangkan!",
        "Badut, saatnya bersenang-senang!",
        "Selamat datang di hari yang baru, Badut!",
        "Badut, siap untuk petualangan hari ini?"
    ]
    while True:
        msg = random.choice(messages)
        message_id = sendMessage(msg)
        if message_id:
            time.sleep(1)  # Tunggu 1 detik sebelum menghapus pesan
            deleteMessage(message_id)  # Hapus pesan setelah waktu tunggu
try:
    main()
except KeyboardInterrupt:
    exit()
