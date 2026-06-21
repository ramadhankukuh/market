# market

Repository data makroekonomi Indonesia dalam format JSON: BI Rate, Inflasi, Pertumbuhan PDB, dan Tingkat Pengangguran Terbuka (TPT). Periode data: 2016–2026.

## 📁 Struktur Data

| File | Deskripsi | Frekuensi |
|---|---|---|
| `makro/bi-rate.json` | BI 7-Day Reverse Repo Rate / BI Rate (%) — sumber Kontan.co.id | Bulanan |
| `makro/inflasi.json` | Inflasi Month-on-Month (%) — sumber BPS | Bulanan |
| `makro/pdb.json` | Pertumbuhan Produk Domestik Bruto Year-on-Year (%) — sumber BPS | Kuartalan |
| `makro/tpt.json` | Tingkat Pengangguran Terbuka (%) — sumber BPS | Kuartalan (Q1 & Q3) |

> Nilai `null` berarti data untuk periode tersebut belum dirilis/tersedia.

## 🚀 Akses Data via CDN

Gunakan **jsDelivr CDN** untuk mengakses file JSON — lebih cepat, ter-cache secara global, dan tidak membebani GitHub secara langsung (dibandingkan `raw.githubusercontent.com`).

```
https://cdn.jsdelivr.net/gh/ramadhankukuh/market@main/makro/bi-rate.json
https://cdn.jsdelivr.net/gh/ramadhankukuh/market@main/makro/inflasi.json
https://cdn.jsdelivr.net/gh/ramadhankukuh/market@main/makro/pdb.json
https://cdn.jsdelivr.net/gh/ramadhankukuh/market@main/makro/tpt.json
```

### Contoh penggunaan (JavaScript)

```js
const res = await fetch('https://cdn.jsdelivr.net/gh/ramadhankukuh/market@main/makro/inflasi.json');
const data = await res.json();
console.log(data.data["2026"]["5"]); // 3.08
```

### Contoh penggunaan (Python)

```python
import requests

url = "https://cdn.jsdelivr.net/gh/ramadhankukuh/market@main/makro/bi-rate.json"
data = requests.get(url).json()
print(data["data"]["2026"]["6"])  # 5.50
```

### Pin ke versi/commit tertentu

jsDelivr meng-cache file `@main` hingga ~12 jam. Untuk hasil yang konsisten (immutable), gunakan tag rilis atau hash commit, contoh:

```
https://cdn.jsdelivr.net/gh/ramadhankukuh/market@466f211/makro/pdb.json
```

Untuk memaksa pembaruan cache `@main` lebih cepat, purge lewat:
```
https://purge.jsdelivr.net/gh/ramadhankukuh/market@main/makro/bi-rate.json
```

## 📊 Sumber Data

- **BI Rate**: Kontan.co.id
- **Inflasi, PDB, TPT**: Badan Pusat Statistik (BPS)

## 📄 Lisensi

Data disusun untuk keperluan riset/analisis publik. Mohon cantumkan sumber asli (BPS / Bank Indonesia) saat menggunakan ulang data ini.