def greedy_coin_change(amount, coins):

    # Menyimpan jumlah koin yang dibutuhkan

    coin_count = []

    

    # Mengurutkan koin berdasarkan nilai terbesar ke terkecil

    coins.sort(reverse=True)

    

    for coin in coins:

        # Menghitung berapa banyak koin yang bisa digunakan

        count = amount // coin

        if count > 0:

            coin_count.append((coin, count))

            # Mengurangi jumlah yang perlu dikembalikan

            amount -= coin * count

    

    # Jika ada sisa uang yang belum dapat dikembalikan

    if amount > 0:

        return "Tidak bisa memberikan uang kembalian dengan koin yang ada."

    

    return coin_count

 

# Uji fungsi dengan uang kembalian 63 dan denominasi koin [25, 10, 5, 1]

amount = int(input("Masukkan Jumlah Uang yang Anda Berikan: "))

coins = [25, 10, 5, 1]

result = greedy_coin_change(amount, coins)

 

# Menampilkan hasil

print(f"Jumlah koin yang dibutuhkan untuk {amount} adalah: {result}")

