<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jadwal Piket Al-Musyaffa'</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            background: #e8f3ff;
            font-family: 'Times New Roman', Times, serif;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 2rem auto;
            padding: 2rem;
            background: rgba(1, 236, 253, 0.95);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
        }

        h1 {
            text-align: center;
            color: #2b4c7e;
            margin-bottom: 2rem;
            font-size: 2.8rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-weight: 600;
        }

        h3 {
            text-align: center;
        }
        .santri-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .santri-card {
            background: rgba(255, 255, 255, 0.95);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            border: 1px solid #e1e8f0;
        }

        .santri-card::before {
            display: none;
        }

        .santri-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
            border-color: #2b4c7e;
        }

        .santri-card h3 {
            color: #2d3436;
            font-weight: 600;
            font-size: 1.2rem;
        }

        .santri-info {
            color: #666;
            line-height: 1.6;
        }

        .santri-info p {
            margin: 0.5rem 0;
        }

        .hari-piket {
            background: linear-gradient(135deg, #2b4c7e, #567ebd);
            color: white;
            padding: 1rem;
            border-radius: 8px;
            margin-bottom: 1.5rem;
            text-align: center;
            font-weight: 500;
            font-size: 1.1rem;
        }

        .tugas-piket {
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px dashed #ccc;
        }

        .tugas-piket ul {
            list-style-type: none;
            padding-left: 0;
        }

        .tugas-piket li {
            margin: 0.3rem 0;
            color: #666;
        }

        @media (max-width: 768px) {
            .container {
                width: 95%;
                padding: 1rem;
            }

            h1 {
                font-size: 2rem;
            }
        }

        /* Tambahan style untuk tombol download */
        .download-section {
            margin-top: 3rem;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            border: 1px solid #e1e8f0;
            text-align: center;
        }

        .download-section h3 {
            color: #2d3436;
            font-size: 1.8rem;
            margin-bottom: 2rem;
            font-weight: 600;
        }

        .download-buttons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .download-btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(135deg, #2b4c7e, #567ebd);
            color: white;
            text-decoration: none;
            border-radius: 8px;
            transition: all 0.3s ease;
            font-weight: 500;
            border: 2px solid transparent;
            box-shadow: 0 4px 15px rgba(43, 76, 126, 0.2);
            min-width: 180px;
        }

        .download-btn:hover {
            background: white;
            color: #2b4c7e;
            border: 2px solid #2b4c7e;
            box-shadow: 0 6px 20px rgba(43, 76, 126, 0.25);
            transform: translateY(-2px);
        }

        @media (max-width: 768px) {
            .download-buttons {
                gap: 1rem;
            }

            .download-btn {
                padding: 10px 20px;
                font-size: 0.9rem;
                min-width: 150px;
            }
        }
    </style>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.3.2/html2canvas.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
</head>
<body>
    <div class="container">
        <h1>Jadwal Piket Al-Musyaffa'</h1>
        <div class="santri-list">
            <div class="santri-card">
                <div class="hari-piket">Senin</div>
                <h3>COWOK</h3>
            </div>
            
            <div class="santri-card">
                <div class="hari-piket">Selasa</div>
                <h3>CEWEK</h3>
            </div>
            
            <div class="santri-card">
                <div class="hari-piket">Rabu</div>
                <h3>COWOK</h3>
            </div>

            <div class="santri-card">
                <div class="hari-piket">Jumat</div>
                <h3>CEWEK</h3>
            </div>

            <div class="santri-card">
                <div class="hari-piket">Sabtu</div>
                <h3>COWOK</h3>
            </div>

            <div class="santri-card">
                <div class="hari-piket">Minggu</div>
                <h3>CEWEK</h3>
            </div>
        </div>

        <!-- Tambahkan section download di bawah santri-list -->
        <div class="download-section">
            <h3>Download Jadwal</h3>
            <div class="download-buttons">
                <a href="javascript:void(0)" onclick="downloadFile('jpg')" class="download-btn">Download JPG</a>
            </div>
        </div>
    </div>

    <script>
        function downloadFile(format) {
            // Create special container for JPG
            const jpgContainer = document.createElement('div');
            jpgContainer.style.cssText = `
                background: white;
                padding: 40px;
                width: 1000px;
                margin: 0 auto;
                border-radius: 15px;
                box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            `;

            // Create title
            const jpgTitle = document.createElement('h1');
            jpgTitle.textContent = "JADWAL PIKET AL-MUSYAFFA'";
            jpgTitle.style.cssText = `
                text-align: center;
                color: #2b4c7e;
                font-size: 36px;
                margin-bottom: 30px;
                font-family: 'Times New Roman', Times, serif;
                text-transform: uppercase;
                letter-spacing: 2px;
                font-weight: bold;
            `;
            jpgContainer.appendChild(jpgTitle);

            // Create grid container
            const jpgGrid = document.createElement('div');
            jpgGrid.style.cssText = `
                display: grid;
                grid-template-columns: repeat(2, 1fr);
                gap: 25px;
                padding: 20px;
            `;

            // Clone and style each card
            const cards = document.querySelectorAll('.santri-card');
            cards.forEach(card => {
                const newCard = document.createElement('div');
                newCard.style.cssText = `
                    background: white;
                    padding: 25px;
                    border-radius: 12px;
                    box-shadow: 0 3px 10px rgba(0,0,0,0.1);
                    text-align: center;
                    border: 2px solid #e1e8f0;
                `;

                const dayElement = document.createElement('div');
                dayElement.textContent = card.querySelector('.hari-piket').textContent;
                dayElement.style.cssText = `
                    background: linear-gradient(135deg, #2b4c7e, #567ebd);
                    color: white;
                    padding: 15px;
                    border-radius: 8px;
                    margin-bottom: 15px;
                    font-weight: bold;
                    font-size: 24px;
                    font-family: 'Times New Roman', Times, serif;
                `;

                const groupElement = document.createElement('h3');
                groupElement.textContent = card.querySelector('h3').textContent;
                groupElement.style.cssText = `
                    color: #2d3436;
                    font-size: 28px;
                    font-weight: bold;
                    font-family: 'Times New Roman', Times, serif;
                    margin: 0;
                `;

                newCard.appendChild(dayElement);
                newCard.appendChild(groupElement);
                jpgGrid.appendChild(newCard);
            });

            jpgContainer.appendChild(jpgGrid);
            document.body.appendChild(jpgContainer);

            const filename = `Jadwal_Piket_Al-Musyaffa`;

            // Convert to JPG with high quality
            html2canvas(jpgContainer, {
                scale: 2,
                useCORS: true,
                letterRendering: true,
                backgroundColor: '#ffffff',
                logging: false,
                width: 1000,
                height: jpgContainer.offsetHeight
            }).then(canvas => {
                const link = document.createElement('a');
                link.download = `${filename}.jpg`;
                link.href = canvas.toDataURL('image/jpeg', 1.0);
                link.click();
                document.body.removeChild(jpgContainer);
            }).catch(err => {
                console.error('Error generating JPG:', err);
                document.body.removeChild(jpgContainer);
            });
        }
    </script>
</body>
</html>
