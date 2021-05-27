# IPv4 Calculator & Mask Converter

Dengan adanya script ini dapat mempermudah kalian semua menggunakannya untuk menghitung IPv4 dan mengetahui Subnet Mask.<br/>
Dan untuk menerapkan script ini kalian bisa mengikuti langkah-langkah yang ada di bawah ini:

## IPv4 Kalkulator

### Penggunaan Dasar

```html
<div class="hasilHitung"></div>
```


```javascript
<script type="text/javascript">
  $(function() {
    const ipaddress   = '192.168.32.64/26';
    const hasilhitung = $('.hasilHitung');

    hasilhitung.subnettingCalculator({
        address: ipaddress
    });
  });
</script>
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
<script type="text/javascript">
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
</script>
```

### Hasil JSON
Kalian juga bisa mendapatkan hasil berupa JSON. Dimana kalian bisa menggunakannya untuk mengubah hasil dari IPv4 Kalkulatornya.
Untuk menerapkannya, kalian dapat menggunakan cara yang ada di bawah ini:

```javascript
<script type="text/javascript">
  $(function() {
    const ipaddress   = '192.168.32.64/26';
    const hasilhitung = $('.hasilHitung');

    const outputJSON = JSON.parse(hasilhitung.subnettingCalculator({
        address: ipaddress,
        outputJSON: true
    })); 

    hasilhitung.html(outputJSON.network);
  });
</script>
```
