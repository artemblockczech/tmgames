
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ваше название страницы</title>
    <!-- Подключение Vue.js через CDN -->
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
    <!-- Предполагаемое подключение TonConnectUI. Убедитесь, что ссылка правильная. -->
   <script src="https://unpkg.com/@tonconnect/sdk@latest/dist/tonconnect-sdk.min.js"></script>

    <style>
        /* Ваши стили здесь */
        #app {
            font-family: Avenir, Helvetica, Arial, sans-serif;
            text-align: center;
            color: #2c3e50;
            background-color: #666;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
        }

        .game-container {
            width: 100vw;
            flex-grow: 1;
            display: flex;
        }

        .game-container iframe {
            flex-grow: 1;
            border: none;
            height: calc(100vh - 150px);
        }

        .ad-container {
            display: block;
            width: 100%;
            height: auto;
        }

        .ad-container img {
            width: 100%;
            height: auto;
        }

        #connectWalletBtn {
            background-color: #333;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 10px 0;
            transition: background-color 0.3s;
        }

        #connectWalletBtn:hover {
            background-color: #555;
        }
    </style>
</head>

<body>
    <div id="app">
        <div class="game-container">
            <iframe src="https://fosiper.com/games/" frameborder="0"></iframe>
        </div>
        <a href="https://www.binance.com/" target="_blank" class="ad-container">
            <img src="https://www.affilibuddy.com/wp-content/uploads/2019/07/binance-referral-program.jpg" alt="Advertisement">
        </a>
        <!-- Добавленная кнопка -->
        <!-- <button id="connectWalletBtn" @click="connectWallet">Подключить кошелек</button> -->
    </div>

    <script>
        new Vue({
            el: '#app',
            name: 'App',
            data() {
                return {
                    tonConnectUI: null
                };
            },
            created() {
                const connector = new TonConnectSDK.TonConnect(),
            methods: {
                async connectWallet() {
                    try {
                        const connectedWallet = await this.tonConnectUI.connectWallet();
                        console.log('Wallet connected:', connectedWallet);
                    } catch (error) {
                        console.error('Error connecting to wallet:', error);
                    }
                }
            }
        });
    </script>
</body>

