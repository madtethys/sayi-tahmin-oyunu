# Sayı Tahmin Oyunu

Bu proje, kullanıcıların 1 ile 100 arasında rastgele seçilen bir sayıyı tahmin etmeye çalıştığı basit bir web tabanlı oyunudur.

## Özellikler

- 1 ile 100 arasında rastgele bir sayı üretilir.
- Kullanıcı, sayıyı tahmin etmek için bir giriş alanına sayı girer ve "Tahmin Et" butonuna basar.
- Kullanıcı doğru sayıyı tahmin edene kadar "Daha büyük" veya "Daha küçük" mesajları görüntülenir.
- Doğru tahmin yapıldığında, kaç denemede doğru tahminin yapıldığı belirtilir.

## Kullanım

1. Projeyi indirip yerel bir sunucuda veya tarayıcınızda çalıştırın.
2. Sayfayı açtığınızda, 1 ile 100 arasında bir sayı tahmin etmeye başlayın.
3. Sayıyı girdikten sonra "Tahmin Et" butonuna tıklayın.
4. İpucu mesajlarını dikkate alarak doğru sayıyı bulmaya çalışın.

## Dosyalar

- `index.html`: Ana HTML dosyasıdır ve oyun burada bulunur.
- `script.js`: Oyun mantığı JavaScript ile burada yazılmıştır (Eğer harici bir dosyada script kullanmak isterseniz).

## Nasıl Çalışır?

- `Math.random()` fonksiyonu ile 1 ile 100 arasında rastgele bir sayı üretilir.
- Kullanıcı bir tahminde bulunduğunda, bu sayı kontrol edilir.
  - Eğer tahmin edilen sayı doğruysa başarı mesajı gösterilir.
  - Eğer tahmin edilen sayı büyükse "Daha küçük bir sayı tahmin edin" mesajı gösterilir.
  - Eğer tahmin edilen sayı küçükse "Daha büyük bir sayı tahmin edin" mesajı gösterilir.

## Örnek

```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayı Tahmin Oyunu</title>
</head>
<body>
    <h1>Sayı Tahmin Oyunu</h1>
    <p>1 ile 100 arasında bir sayı tahmin edin!</p>
    <input type="number" id="guessInput" placeholder="Tahmininizi girin">
    <button onclick="checkGuess()">Tahmin Et</button>
    <p id="message"></p>

    <script>
        const randomNumber = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        function checkGuess() {
            const userGuess = document.getElementById("guessInput").value;
            attempts++;
            if (userGuess == randomNumber) {
                document.getElementById("message").innerText = `Tebrikler! ${attempts} denemede doğru tahmin ettiniz.`;
            } else if (userGuess > randomNumber) {
                document.getElementById("message").innerText = "Daha küçük bir sayı tahmin edin.";
            } else {
                document.getElementById("message").innerText = "Daha büyük bir sayı tahmin edin.";
            }
        }
    </script>
</body>
</html>
```

## Katkıda Bulunma

Bu projeye katkıda bulunmak isterseniz, lütfen pull request gönderin veya bir issue açın. Her türlü geri bildirime açığız!

## Lisans

Bu proje [MIT Lisansı](LICENSE) altında lisanslanmıştır.

