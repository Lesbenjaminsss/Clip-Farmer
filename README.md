# ✂️ Klip Makinesi

**Türkçe · English · Español**

[Türkçe](#türkçe) | [English](#english) | [Español](#español)

Made by / Yapan / Hecho por: [Lesbenjaminsss](https://github.com/Lesbenjaminsss)

🔗 **Demo / Canlı demo / Demostración:** <http://185.34.101.41:8080/>

---

## Türkçe

> Videolardan en dikkat çekici anları otomatik bulan ve **YouTube Shorts** için dikey (9:16) klibe çeviren, tamamen tarayıcıda çalışan araç.

### Özellikler

- **Otomatik en iyi an bulma:** Ses seviyesi ve görüntü hareketi analiz edilir, en yüksek puanlı bölümler klip olarak önerilir.
- **Ayarlanabilir klip:** Süre (15 / 30 / 45 / 59 sn) ve klip sayısı (3 / 5 / 8) seçilebilir.
- **Dikey 9:16 çıktı:** 720×1280 çözünürlükte, Shorts uyumlu.
- **Ekran + kamera düzeni:** Videodaki ekran ve kamera (facecam) bölgelerini kendin işaretlersin.
  - Ekran, oranı bozulmadan sığdırılır ya da kırpılarak doldurulur.
  - Kamera üstte, altta ya da köşede yüzen olarak yerleştirilir; önizlemede sürükleyip büyütüp küçültebilirsin.
  - Kamera şekli: dikdörtgen, yuvarlak köşe, daire.
  - Arka plan: bulanık ya da düz renk.
- **Sunucu yok:** Videon bilgisayarından çıkmaz. Her şey tarayıcıda işlenir.
- **Tek dosya:** Derleme, paket kurulumu ya da bağımlılık gerekmez.

### Kullanım

1. `index.html` dosyasını tarayıcıda aç (ya da GitHub Pages adresini).
2. Video dosyasını sürükleyip bırak, ya da doğrudan bir `.mp4` / `.webm` adresi yapıştır.
3. Videoda kamera varsa **“Videoda kamera var”** kutusunu işaretle. Kaynak bölgeleri alanında mavi çerçeveyi ekrana, yeşil çerçeveyi kameraya oturt.
4. Telefon önizlemesinde ekranı ve kamerayı istediğin yere sürükle.
5. **“En iyi anları bul”** düğmesine bas.
6. Klipleri **“Oynat”** ile izle, **“Shorts indir”** ile kaydet.

### GitHub Pages ile yayınlama

1. Bu depoyu GitHub’a yükle.
2. **Settings → Pages** bölümüne gir.
3. **Source** olarak `main` dalını ve `/ (root)` klasörünü seç.
4. Birkaç dakika sonra site `https://Lesbenjaminsss.github.io/<depo-adı>/` adresinde yayında olur.

### Nasıl çalışıyor?

| Adım | Yöntem |
|------|--------|
| Ses analizi | Web Audio API ile ses çözülür, her saniyenin RMS (ses şiddeti) değeri hesaplanır. |
| Hareket analizi | Video belirli aralıklarla 32×18 küçük kareye çizilir, ardışık kareler arasındaki piksel farkı ölçülür. |
| Puanlama | `0.55 × ses + 0.45 × hareket`, 5 saniyelik ortalama ile yumuşatılır. |
| Seçim | Seçilen süredeki pencereler taranır, çakışmayan en yüksek puanlı bölümler alınır. |
| Dikey çıktı | Video `canvas` üzerinde 720×1280 olarak yeniden çizilir; `captureStream` ve `MediaRecorder` ile kaydedilir. |

### Sınırlamalar

- “Otomatik analiz” **içeriği anlamaz**. Sadece en gürültülü ve hareketli anları bulur; en komik ya da en bilgilendirici an olmayabilir. Sonuçları gözden geçir.
- **YouTube bağlantıları analiz edilemez.** Tarayıcıdan YouTube videosu indirilemez; videoyu önce kendin indirip dosya olarak yükle.
- Başka bir siteden gelen video adresi **CORS** izni vermiyorsa analiz ve indirme çalışmaz; dosya olarak yükle.
- Kayıt **gerçek zamanlıdır**: 30 saniyelik klip yaklaşık 30 saniye sürer.
- Çıktı biçimi tarayıcıya bağlı olarak `.webm` (Chrome, Edge, Firefox) ya da `.mp4` olur.
- Uzun ve büyük videolarda ses çözme çok bellek kullanır.
- Safari’de `captureStream` ve bulanık arka plan desteği sınırlıdır; Chrome, Edge ya da Firefox önerilir.

### Yol haritası

- [ ] Transkripte göre içerik temelli an seçimi
- [ ] Otomatik altyazı yakma
- [ ] MP4 çıktı ve toplu indirme
- [ ] Yüz algılayarak kamera bölgesini otomatik bulma

---

## English

> A browser-only tool that automatically finds the most eye-catching moments in a video and exports them as vertical (9:16) clips for **YouTube Shorts**.

### Features

- **Automatic highlight detection:** Audio loudness and visual motion are analyzed, and the highest-scoring segments are suggested as clips.
- **Adjustable clips:** Choose the length (15 / 30 / 45 / 59 s) and the number of clips (3 / 5 / 8).
- **Vertical 9:16 output:** 720×1280 resolution, Shorts-ready.
- **Screen + camera layout:** You mark the screen and camera (facecam) regions in the source video.
  - The screen is fitted without distortion or filled with cropping.
  - The camera can go on top, at the bottom, or floating in a corner; drag and resize it in the preview.
  - Camera shape: rectangle, rounded corners, circle.
  - Background: blurred or solid color.
- **No server:** Your video never leaves your computer. Everything is processed in the browser.
- **Single file:** No build step, no package install, no dependencies.

### Usage

1. Open `index.html` in your browser (or visit the GitHub Pages URL).
2. Drag and drop a video file, or paste a direct `.mp4` / `.webm` URL.
3. If the video has a camera, tick **“Videoda kamera var”** (the “camera in video” checkbox). In the source regions panel, place the blue frame on the screen and the green frame on the camera.
4. Drag the screen and the camera wherever you want in the phone preview.
5. Press **“En iyi anları bul”** (find the best moments).
6. Watch clips with **“Oynat”** (play) and save them with **“Shorts indir”** (download as Short).

### Publishing with GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, choose the `main` branch and the `/ (root)` folder.
4. After a few minutes the site is live at `https://Lesbenjaminsss.github.io/<repo-name>/`.

### How it works

| Step | Method |
|------|--------|
| Audio analysis | The audio is decoded with the Web Audio API and the RMS (loudness) of every second is computed. |
| Motion analysis | The video is drawn at intervals onto a tiny 32×18 frame, and the pixel difference between consecutive frames is measured. |
| Scoring | `0.55 × audio + 0.45 × motion`, smoothed with a 5-second average. |
| Selection | Windows of the chosen length are scanned and the best non-overlapping segments are picked. |
| Vertical output | The video is redrawn on a 720×1280 `canvas` and recorded with `captureStream` and `MediaRecorder`. |

### Limitations

- The “automatic analysis” **does not understand content**. It only finds the loudest and most active moments, which may not be the funniest or most informative ones. Review the results.
- **YouTube links cannot be analyzed.** A browser cannot download YouTube videos; download the video yourself first and upload it as a file.
- If a video URL from another site does not allow **CORS**, analysis and export will not work; upload it as a file instead.
- Recording is **real time**: a 30-second clip takes about 30 seconds.
- The output format is `.webm` (Chrome, Edge, Firefox) or `.mp4`, depending on the browser.
- Decoding the audio of long, large videos uses a lot of memory.
- Safari has limited support for `captureStream` and the blurred background; Chrome, Edge, or Firefox is recommended.

### Roadmap

- [ ] Content-based moment selection from a transcript
- [ ] Automatic burned-in captions
- [ ] MP4 output and batch download
- [ ] Automatic camera region detection using face detection

---

## Español

> Una herramienta que funciona solo en el navegador, encuentra automáticamente los momentos más llamativos de un video y los exporta como clips verticales (9:16) para **YouTube Shorts**.

### Características

- **Detección automática de momentos destacados:** Se analizan el volumen del audio y el movimiento de la imagen, y se proponen como clips los tramos con mayor puntuación.
- **Clips ajustables:** Elige la duración (15 / 30 / 45 / 59 s) y la cantidad de clips (3 / 5 / 8).
- **Salida vertical 9:16:** Resolución de 720×1280, lista para Shorts.
- **Diseño de pantalla + cámara:** Tú marcas las regiones de la pantalla y de la cámara (facecam) en el video original.
  - La pantalla se ajusta sin deformarse o se rellena recortando.
  - La cámara puede ir arriba, abajo o flotando en una esquina; arrástrala y cambia su tamaño en la vista previa.
  - Forma de la cámara: rectángulo, esquinas redondeadas, círculo.
  - Fondo: desenfocado o de color sólido.
- **Sin servidor:** Tu video nunca sale de tu computadora. Todo se procesa en el navegador.
- **Un solo archivo:** Sin compilación, sin instalar paquetes, sin dependencias.

### Uso

1. Abre `index.html` en tu navegador (o la dirección de GitHub Pages).
2. Arrastra y suelta un archivo de video, o pega una dirección directa `.mp4` / `.webm`.
3. Si el video tiene cámara, marca la casilla **“Videoda kamera var”** (“hay cámara en el video”). En el panel de regiones de origen, coloca el marco azul sobre la pantalla y el marco verde sobre la cámara.
4. En la vista previa del teléfono, arrastra la pantalla y la cámara donde quieras.
5. Pulsa **“En iyi anları bul”** (buscar los mejores momentos).
6. Mira los clips con **“Oynat”** (reproducir) y guárdalos con **“Shorts indir”** (descargar como Short).

### Publicar con GitHub Pages

1. Sube este repositorio a GitHub.
2. Ve a **Settings → Pages**.
3. En **Source**, elige la rama `main` y la carpeta `/ (root)`.
4. Tras unos minutos, el sitio estará disponible en `https://Lesbenjaminsss.github.io/<nombre-del-repo>/`.

### Cómo funciona

| Paso | Método |
|------|--------|
| Análisis de audio | El audio se decodifica con la Web Audio API y se calcula el RMS (intensidad) de cada segundo. |
| Análisis de movimiento | El video se dibuja a intervalos en un cuadro diminuto de 32×18 y se mide la diferencia de píxeles entre cuadros consecutivos. |
| Puntuación | `0.55 × audio + 0.45 × movimiento`, suavizado con un promedio de 5 segundos. |
| Selección | Se recorren ventanas de la duración elegida y se toman los mejores tramos que no se solapan. |
| Salida vertical | El video se redibuja en un `canvas` de 720×1280 y se graba con `captureStream` y `MediaRecorder`. |

### Limitaciones

- El “análisis automático” **no entiende el contenido**. Solo encuentra los momentos más ruidosos y con más movimiento, que pueden no ser los más graciosos ni los más informativos. Revisa los resultados.
- **Los enlaces de YouTube no se pueden analizar.** Un navegador no puede descargar videos de YouTube; descarga primero el video tú mismo y súbelo como archivo.
- Si la dirección de un video de otro sitio no permite **CORS**, el análisis y la exportación no funcionarán; súbelo como archivo.
- La grabación es **en tiempo real**: un clip de 30 segundos tarda unos 30 segundos.
- El formato de salida es `.webm` (Chrome, Edge, Firefox) o `.mp4`, según el navegador.
- Decodificar el audio de videos largos y pesados consume mucha memoria.
- Safari tiene soporte limitado para `captureStream` y el fondo desenfocado; se recomienda Chrome, Edge o Firefox.

### Hoja de ruta

- [ ] Selección de momentos por contenido a partir de una transcripción
- [ ] Subtítulos automáticos incrustados
- [ ] Salida MP4 y descarga por lotes
- [ ] Detección automática de la región de la cámara mediante detección de rostros

---

## Lisans / License / Licencia

[MIT](LICENSE) © 2026 [Lesbenjaminsss](https://github.com/Lesbenjaminsss)
