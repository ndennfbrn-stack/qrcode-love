# qrcode-love
QR Code Love - Website Generator QR Code dengan Teks, Foto, dan Trebedit APK Integration
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>QR Code Love - Trebedit</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="header-content">
            <div class="logo">
                <span class="heart">💗</span>
                <h1>QR Code Love</h1>
                <span class="heart">💗</span>
            </div>
            <p class="tagline">Buat QR Code dengan Cinta untuk Trebedit</p>
        </div>
    </header>

    <!-- Main Container -->
    <main class="container">
        <!-- Input Section -->
        <section class="input-section">
            <h2>✨ Buat QR Code Anda</h2>
            
            <div class="form-group">
                <label for="textInput">📝 Masukkan Teks atau URL:</label>
                <textarea 
                    id="textInput" 
                    placeholder="Contoh: Halo Sayang! Atau link ke Trebedit..." 
                    rows="3"
                ></textarea>
            </div>

            <div class="form-group">
                <label for="photoInput">📸 Upload Foto (Opsional):</label>
                <div class="file-input-wrapper">
                    <input 
                        type="file" 
                        id="photoInput" 
                        accept="image/*"
                    >
                    <span class="file-label">Pilih Foto</span>
                </div>
                <div id="photoPreview" class="photo-preview"></div>
            </div>

            <div class="form-group">
                <label for="nameInput">👤 Nama Pembuat (Opsional):</label>
                <input 
                    type="text" 
                    id="nameInput" 
                    placeholder="Masukkan nama Anda"
                >
            </div>

            <button id="generateBtn" class="btn btn-primary">
                💖 Generate QR Code
            </button>
        </section>

        <!-- Preview Section -->
        <section id="previewSection" class="preview-section hidden">
            <h2>👀 Preview Sebelum Disimpan</h2>
            
            <div class="preview-card">
                <div class="preview-content">
                    <div id="photoPreviewBox" class="preview-photo"></div>
                    <div class="preview-info">
                        <p class="preview-text"></p>
                        <p class="preview-name"></p>
                    </div>
                </div>
                <div id="qrcodePreview" class="qrcode-preview"></div>
            </div>

            <div class="button-group">
                <button id="saveBtn" class="btn btn-success">💾 Simpan</button>
                <button id="editBtn" class="btn btn-secondary">✏️ Edit</button>
            </div>
        </section>

        <!-- QR Code Result Section -->
        <section id="resultSection" class="result-section hidden">
            <h2>💖 QR Code Berhasil Disimpan!</h2>
            
            <div class="result-card">
                <div id="qrcodeResult" class="qrcode-result"></div>
                <div class="result-info">
                    <p id="resultText" class="result-text"></p>
                    <p id="resultName" class="result-name"></p>
                    <p id="resultDate" class="result-date"></p>
                </div>
            </div>

            <div class="button-group">
                <button id="shareBtn" class="btn btn-info">📤 Bagikan ke Trebedit</button>
                <button id="newBtn" class="btn btn-primary">➕ Buat Baru</button>
                <button id="viewHistoryBtn" class="btn btn-secondary">📚 Lihat Riwayat</button>
            </div>
        </section>

        <!-- History Section -->
        <section id="historySection" class="history-section hidden">
            <h2>📚 Riwayat QR Code</h2>
            
            <div class="history-controls">
                <button id="backHistoryBtn" class="btn btn-secondary">← Kembali</button>
                <button id="clearHistoryBtn" class="btn btn-danger">🗑️ Hapus Semua</button>
            </div>

            <div id="historyList" class="history-list"></div>
        </section>
    </main>

    <!-- Modal untuk Detail Riwayat -->
    <div id="detailModal" class="modal hidden">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h3>Detail QR Code</h3>
            <div id="modalBody" class="modal-body"></div>
            <div class="modal-buttons">
                <button id="shareFromModal" class="btn btn-info">📤 Bagikan</button>
                <button id="deleteFromModal" class="btn btn-danger">🗑️ Hapus</button>
            </div>
        </div>
    </div>

    <!-- Success Notification -->
    <div id="notification" class="notification hidden"></div>

    <script src="storage.js"></script>
    <script src="script.js"></script>
</body>
</html>
