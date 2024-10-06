"Ultrasonik Mesafe Sensörü" kullanarak mesafe ölçen basit bir Arduino uygulaması:::::
Çalışma Prensibi:
Trig pini üzerinden ses dalgası gönderilir.
Echo pini, geri dönen yankıyı algılar ve sinyalin geri dönme süresini ölçer.
Bu süre kullanılarak, ses dalgasının havadaki hızına dayanarak mesafe hesaplanır.
Sonuç, bilgisayar ekranına santimetre cinsinden yazdırılır.

Bekleme süresi:
delay(500);: 500 milisaniyelik bir bekleme uygulanır. Bu, sensörün her ölçüm yapması arasındaki süreyi belirler.
Sonuçları ekrana yazdırma:

Serial.print("Mesafe: ");: Mesafe verisinin başına "Mesafe: " yazısı eklenir.
Serial.print(distance);: Hesaplanan mesafe değeri yazdırılır.
Serial.println(" cm");: Son olarak mesafenin ölçü birimi olan "cm" yazdırılır.

loop() Fonksiyonu:
Sensörün tetiklenmesi:

 digitalWrite(TRIG_PIN, LOW);: Trig pini LOW (düşük) seviyeye çekilerek sensör sıfırlanır.
 delayMicroseconds(2);: 2 mikro saniyelik kısa bir gecikme uygulanır.
 digitalWrite(TRIG_PIN, HIGH);: Trig pini HIGH (yüksek) seviyeye çekilerek ses dalgası gönderilir.
 delayMicroseconds(10);: 10 mikro saniye boyunca Trig pini yüksek tutulur, bu sırada ultrasonik sinyal gönderilir.
 digitalWrite(TRIG_PIN, LOW);: Trig pini tekrar LOW seviyeye çekilerek sinyal gönderme işlemi durdurulur.
