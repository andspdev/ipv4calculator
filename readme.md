# IPv4 Calculator & Mask Converter

Copyright &copy; 2021 Andreas Pandu Pamungkas

Dengan adanya script ini dapat mempermudah kalian semua menggunakannya untuk menghitung IPv4 dan mengetahui Subnet Mask.


Sebelum itu agar script ini dapat digunakan, kalian jangan lupa untuk memasang:

```javascript
<script type="text/javascript" src="js/jquery.min.js"></script>
```
```javascript
<script type="text/javascript" src="js/ipv4calculator.min.js"></script>
```

Jika sudah kalian dapat memulai untuk mengikuti langkah-langkah berikut ini:

## Demo
https://andspdev.github.io/ipv4calculator/

## IPv4 Kalkulator

### Penggunaan Dasar

```html
<div class="hasilHitung"></div>
```


```javascript
$(function() {
  const ipaddress   = '192.168.32.64/26';
  const hasilhitung = $('.hasilHitung');

  hasilhitung.subnettingCalculator({
      address: ipaddress
  });
});
```

### Teks Default
Secara default teks yang sudah terpasang akan seperti ini:

```javascript
[
    'Network',
    'Subnet Mask', 
    'Wildcard Mask',
    'Broadcast',
    'Hosts Valid', 
    'Hosts',
    'Network', 
    'Subnetmask',
    'Wildcard Mask',
    'First Host', 
    'Last Host',
    'Broadcast'
]
```

### Mengubah Teks
Dan kalian bisa mengcustom teks tersebut dengan cara di bawah ini:

```javascript
$(function() {
  const ipaddress   = '192.168.32.64/26';
  const hasilhitung = $('.hasilHitung');

  hasilhitung.subnettingCalculator({
      address: ipaddress,
      customText: [
        'Network',
        'Subnet Mask', 
        'Wildcard Mask',
        'Broadcast',
        'Hosts Valid', 
        'Hosts',
        'Network', 
        'Subnetmask',
        'Wildcard Mask',
        'First Host', 
        'Last Host',
        'Broadcast'
      ]
  });
});
```

### Hasil JSON
Kalian juga bisa mendapatkan hasil berupa JSON. Dimana kalian bisa menggunakannya untuk mengubah hasil dari IPv4 Kalkulatornya.
Untuk menerapkannya, kalian dapat menggunakan cara yang ada di bawah ini:

```javascript
$(function() {
  const ipaddress   = '192.168.32.64/26';
  const hasilhitung = $('.hasilHitung');

  const outputJSON = JSON.parse(hasilhitung.subnettingCalculator({
      address: ipaddress,
      outputJSON: true
  })); 

  hasilhitung.html(outputJSON.network);
});
```

```JSON
{
  "network":"192.168.32.64",
  "subnetmask":"255.255.255.192",
  "wildcardmask":"0.0.0.63",
  "broadcast":"192.168.32.127",
  "hosts_valid":62,
  "hosts":"192.168.32.65 - 192.168.32.126",
  "binary":{
    "network":"11000000.10101000.00100000.01000000",
    "subnetmask":"11111111.11111111.11111111.11000000",
    "first_host":"00000000.00000000.00000000.00111111",
    "last_host":"11000000.10101000.00100000.01000001",
    "broadcast":"11000000.10101000.00100000.01111110"
  }
}
```


## Mask Converter

### Penggunaan Dasar

```html
<div class="hasilHitung"></div>
```


```javascript
$(function() {
  const subnetmask  = '255.255.255.128';
  const hasilhitung = $('.hasilHitung');

  hasilhitung.subnettingCalculator({
      maskCalculator: subnetmask
  });
});
```

### Teks Default
Secara default teks yang sudah terpasang akan seperti ini:

```javascript
[
    'Subnet Mask',
    'Wildcard Mask',
    'Slash Notation',
    'Subnet Mask',
    'Wildcard Mask'
]
```

### Mengubah Teks
Dan kalian bisa mengcustom teks tersebut dengan cara di bawah ini:

```javascript
$(function() {
  const subnetmask  = '255.255.255.128';
  const hasilhitung = $('.hasilHitung');

  hasilhitung.subnettingCalculator({
      maskCalculator: subnetmask,
      customTextSubnetmask: [
          'Subnet Mask',
          'Wildcard Mask',
          'Slash Notation',
          'Subnet Mask',
          'Wildcard Mask'
      ]
  });
});
```

### Hasil JSON
Kalian juga bisa mendapatkan hasil berupa JSON. Dimana kalian bisa menggunakannya untuk mengubah hasil dari Mask Converternya.
Untuk menerapkannya, kalian dapat menggunakan cara yang ada di bawah ini:

```javascript
$(function() {
  const subnetmask  = '255.255.255.128';
  const hasilhitung = $('.hasilHitung');

  const outputJSON = JSON.parse(hasilhitung.subnettingCalculator({
      maskCalculator: subnetmask,
      outputJSON: true
  })); 

  hasilhitung.html(outputJSON.subnetmask);
});
```

```JSON
{
  "subnetmask":"255.255.255.128",
  "wildcardmask":"0.0.0.127",
  "slash_notation":"/25",
  "binary":{
    "subnetmask":"11111111.11111111.11111111.10000000",
    "wildcardmask":"00000000.00000000.00000000.01111111"
  }
}
```
