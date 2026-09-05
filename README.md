<html lang="en" id="html-root">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vestify Pro - Manual Payout Platform</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
        }
    </script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .perspective-1000 { perspective: 1000px; }
        .transform-style-3d { transform-style: preserve-3d; }
        .backface-hidden { backface-visibility: hidden; }
        .rotate-y-180 { transform: rotateY(180deg); }
    </style>
</head>
<body class="bg-gray-100 dark:bg-zinc-950 flex justify-center items-center min-h-screen transition-colors duration-300">

    <div class="w-full max-w-md bg-white dark:bg-zinc-900 min-h-screen shadow-2xl flex flex-col justify-between relative pb-16 transition-colors duration-300 overflow-hidden">
        
        <div>
            <div class="flex justify-between items-center px-4 py-3 border-b dark:border-zinc-800 bg-white dark:bg-zinc-900 sticky top-0 z-20">
                <div class="flex items-center gap-2">
                    <span class="text-indigo-600 dark:text-indigo-400 font-extrabold text-2xl tracking-tighter">Vestify<span class="text-black dark:text-white">.</span></span>
                    <span class="bg-indigo-100 dark:bg-indigo-950 text-indigo-700 dark:text-indigo-300 text-[10px] font-bold px-2 py-0.5 rounded-full">PRO</span>
                </div>
                <div class="flex items-center space-x-3 text-gray-600 dark:text-gray-300">
                    <button onclick="toggleDarkMode()" class="w-8 h-8 rounded-full bg-gray-100 dark:bg-zinc-800 flex items-center justify-center text-sm hover:bg-gray-200 dark:hover:bg-zinc-700 transition">
                        <i id="theme-icon" class="fa-solid fa-moon"></i>
                    </button>
                    <div class="w-7 h-7 bg-indigo-600 text-white rounded-full flex items-center justify-center font-semibold text-sm">V</div>
                </div>
            </div>

            <div class="p-4" id="main-content">
                <h2 class="text-center font-bold text-lg mb-3 text-gray-800 dark:text-white">Manual Payout Request</h2>

                <div class="w-full h-44 perspective-1000 mb-5">
                    <div id="card-inner" class="relative w-full h-full duration-500 transform-style-3d shadow-xl rounded-2xl">
                        
                        <div class="absolute inset-0 bg-gradient-to-tr from-indigo-950 via-indigo-800 to-purple-900 rounded-2xl p-5 text-white flex flex-col justify-between backface-hidden overflow-hidden border border-indigo-500/30">
                            <div class="absolute -right-6 -top-6 w-32 h-32 bg-white/10 rounded-full blur-xl pointer-events-none"></div>
                            <div class="flex justify-between items-center">
                                <i class="fa-solid fa-sim-card text-yellow-300 text-2xl"></i>
                                <div class="text-right">
                                    <span id="card-brand-logo" class="font-extrabold italic text-xs tracking-widest uppercase block">VISA</span>
                                    <span id="preview-amount" class="text-emerald-400 font-bold text-xs">$0.00</span>
                                </div>
                            </div>
                            <div class="font-mono text-lg tracking-widest drop-shadow" id="preview-number">•••• •••• •••• ••••</div>
                            <div class="flex justify-between items-end text-xs">
                                <div>
                                    <p class="text-[9px] uppercase tracking-wider text-indigo-200">Cardholder Name</p>
                                    <p class="font-bold tracking-wide uppercase truncate max-w-[170px]" id="preview-name">JOHN DOE</p>
                                </div>
                                <div>
                                    <p class="text-[9px] uppercase tracking-wider text-indigo-200">Expires</p>
                                    <p class="font-mono font-bold" id="preview-expiry">MM/YY</p>
                                </div>
                            </div>
                        </div>

                        <div class="absolute inset-0 bg-gradient-to-tr from-zinc-900 via-indigo-950 to-zinc-900 rounded-2xl p-5 text-white flex flex-col justify-between backface-hidden rotate-y-180 border border-indigo-500/30">
                            <div class="w-full h-9 bg-black/80 -mx-5 mt-2"></div>
                            <div class="flex items-center gap-3 bg-white/10 p-2 rounded-lg">
                                <div class="w-12 h-6 bg-white text-black font-mono font-bold flex items-center justify-center rounded text-sm" id="preview-cvc">•••</div>
                                <span class="text-[10px] text-gray-300">Authorized Security CVV / CVC</span>
                            </div>
                            <div class="text-[9px] text-gray-400 text-center">Vestify Pro Encrypted Manual Node</div>
                        </div>

                    </div>
                </div>
                
                <div class="bg-indigo-50 dark:bg-indigo-950/40 border border-indigo-500/50 rounded-lg p-2.5 text-center text-xs text-indigo-800 dark:text-indigo-300 mb-5 flex items-center justify-center gap-2">
                    <i class="fa-solid fa-lock"></i>
                    <span>Manual withdrawal processed securely via admin review</span>
                </div>

                <form id="payout-form" class="space-y-3.5" onsubmit="initiateOTP(event)">
                    <div class="flex gap-3">
                        <div class="w-2/3">
                            <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Cardholder name</label>
                            <input type="text" id="cardholder-name" placeholder="JOHN DOE" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-2.5 text-sm focus:outline-none focus:border-indigo-500 uppercase" oninput="updateName(this)">
                        </div>
                        <div class="w-1/3">
                            <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Amount ($)</label>
                            <input type="number" id="payout-amount" placeholder="150" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-2.5 text-sm focus:outline-none focus:border-indigo-500 font-mono" oninput="updateAmount(this)">
                        </div>
                    </div>

                    <div>
                        <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Card number</label>
                        <input type="text" id="card-number" placeholder="1234 5678 9012 3456" maxlength="19" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-2.5 text-sm focus:outline-none focus:border-indigo-500 font-mono" oninput="formatCardNumber(this)">
                    </div>

                    <div class="flex gap-3">
                        <div class="w-1/2">
                            <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Expiration</label>
                            <input type="text" id="expiry-date" placeholder="MM/YY" maxlength="5" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-2.5 text-sm focus:outline-none focus:border-indigo-500 font-mono" oninput="formatExpiry(this)">
                        </div>
                        <div class="w-1/2">
                            <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">CVC Code</label>
                            <input type="password" id="cvc" placeholder="CVC" maxlength="4" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-2.5 text-sm focus:outline-none focus:border-indigo-500 font-mono" onfocus="flipCard(true)" onblur="flipCard(false)" oninput="updateCvc(this)">
                        </div>
                    </div>

                    <button type="submit" id="submit-btn" class="w-full bg-indigo-600 text-white font-semibold py-3 rounded-xl hover:bg-indigo-700 transition mt-2 shadow-md flex items-center justify-center gap-2 text-sm">
                        <span>Request Manual Payout</span>
                    </button>
                </form>

            </div>

            <div id="success-screen" class="hidden p-8 text-center flex flex-col items-center justify-center min-h-[450px]">
                <div class="w-16 h-16 bg-emerald-100 dark:bg-emerald-950/50 text-emerald-600 dark:text-emerald-400 rounded-full flex items-center justify-center text-3xl mb-4 animate-bounce">
                    <i class="fa-solid fa-check"></i>
                </div>
                <h3 class="text-xl font-bold text-gray-800 dark:text-white mb-2">Request Submitted!</h3>
                <p class="text-xs text-gray-500 dark:text-gray-400 mb-6">Your manual payout request of <span id="success-amount" class="font-bold text-indigo-600"></span> to card ending <span id="last-four" class="font-bold"></span> is pending admin review.</p>
                <button onclick="resetForm()" class="bg-indigo-600 text-white text-xs font-semibold px-6 py-3 rounded-xl hover:bg-indigo-700 transition">New Request</button>
            </div>
        </div>

        <div class="absolute bottom-0 left-0 right-0 bg-white dark:bg-zinc-900 border-t dark:border-zinc-800 flex justify-around py-2.5 text-gray-500 dark:text-gray-400 text-xs">
            <div class="flex flex-col items-center text-indigo-600 dark:text-indigo-400 cursor-pointer">
                <i class="fa-solid fa-house text-base"></i>
                <span>Home</span>
            </div>
            <div class="flex flex-col items-center cursor-pointer">
                <i class="fa-solid fa-clock-rotate-left text-base"></i>
                <span>History</span>
            </div>
            <div class="flex flex-col items-center cursor-pointer">
                <i class="fa-regular fa-bell text-base"></i>
                <span>Alerts</span>
            </div>
            <div class="flex flex-col items-center cursor-pointer">
                <div class="w-5 h-5 bg-indigo-600 text-white rounded-full flex items-center justify-center text-[10px] font-semibold">V</div>
                <span>Profile</span>
            </div>
        </div>

    </div>

    <div id="otp-modal" class="fixed inset-0 bg-black/60 backdrop-blur-sm hidden flex items-center justify-center z-50 p-4">
        <div class="bg-white dark:bg-zinc-900 rounded-2xl p-6 w-full max-w-sm shadow-2xl border dark:border-zinc-800 text-center">
            <div class="w-12 h-12 bg-indigo-100 dark:bg-indigo-950 text-indigo-600 dark:text-indigo-400 rounded-full flex items-center justify-center text-xl mx-auto mb-3">
                <i class="fa-solid fa-shield-cat"></i>
            </div>
            <h3 class="font-bold text-base text-gray-800 dark:text-white mb-1">Security Verification</h3>
            <p class="text-xs text-gray-500 dark:text-gray-400 mb-4">Enter the 6-digit confirmation PIN sent to your registered device.</p>
            <input type="text" id="otp-input" maxlength="6" placeholder="• • • • • •" class="w-full text-center tracking-widest font-mono text-lg border dark:border-zinc-700 bg-gray-50 dark:bg-zinc-800 rounded-xl p-3 mb-4 text-gray-900 dark:text-white focus:outline-none focus:border-indigo-500">
            <button onclick="verifyOTP()" id="verify-btn" class="w-full bg-indigo-600 text-white font-semibold py-3 rounded-xl hover:bg-indigo-700 transition text-xs shadow-md">Confirm & Dispatch</button>
        </div>
    </div>

    <script>
        function toggleDarkMode() {
            const root = document.getElementById('html-root');
            const icon = document.getElementById('theme-icon');
            root.classList.toggle('dark');
            icon.className = root.classList.contains('dark') ? "fa-solid fa-sun" : "fa-solid fa-moon";
        }

        function updateName(input) {
            document.getElementById('preview-name').innerText = input.value ? input.value : 'JOHN DOE';
        }

        function updateAmount(input) {
            document.getElementById('preview-amount').innerText = input.value ? `$${Number(input.value).toLocaleString()}` : '$0.00';
        }

        function updateCvc(input) {
            document.getElementById('preview-cvc').innerText = input.value ? input.value : '•••';
        }

        function flipCard(showBack) {
            const cardInner = document.getElementById('card-inner');
            if (showBack) {
                cardInner.style.transform = 'rotateY(180deg)';
            } else {
                cardInner.style.transform = 'rotateY(0deg)';
            }
        }

        function formatCardNumber(input) {
            let value = input.value.replace(/\D/g, '');
            input.value = value.match(/.{1,4}/g)?.join(' ') || '';
            document.getElementById('preview-number').innerText = input.value ? input.value : '•••• •••• •••• ••••';
            
            const brandLogo = document.getElementById('card-brand-logo');
            if (value.startsWith('4')) brandLogo.innerText = "VISA";
            else if (value.startsWith('5') || value.startsWith('2')) brandLogo.innerText = "MASTERCARD";
            else if (value.startsWith('6')) brandLogo.innerText = "DISCOVER";
            else if (value.startsWith('3')) brandLogo.innerText = "JCB";
            else brandLogo.innerText = "VISA";
        }

        function formatExpiry(input) {
            let value = input.value.replace(/\D/g, '');
            if (value.length >= 3) {
                input.value = value.slice(0, 2) + '/' + value.slice(2, 4);
            } else {
                input.value = value;
            }
            document.getElementById('preview-expiry').innerText = input.value ? input.value : 'MM/YY';
        }

        function initiateOTP(e) {
            e.preventDefault();
            document.getElementById('otp-modal').classList.remove('hidden');
        }

        function verifyOTP() {
            const otp = document.getElementById('otp-input').value;
            if(otp.length < 4) {
                alert('Please enter valid security code.');
                return;
            }

            const verifyBtn = document.getElementById('verify-btn');
            verifyBtn.innerHTML = `<i class="fa-solid fa-spinner fa-spin"></i> Submitting to Admin...`;

            setTimeout(() => {
                document.getElementById('otp-modal').classList.add('hidden');
                document.getElementById('payout-form').parentElement.classList.add('hidden');
                
                const amount = document.getElementById('payout-amount').value;
                const cardNum = document.getElementById('card-number').value;

                document.getElementById('success-amount').innerText = `$${amount}`;
                document.getElementById('last-four').innerText = cardNum.slice(-4);
                document.getElementById('success-screen').classList.remove('hidden');
                
                verifyBtn.innerHTML = `Confirm & Dispatch`;
                document.getElementById('otp-input').value = '';
            }, 1500);
        }

        function resetForm() {
            document.getElementById('payout-form').reset();
            document.getElementById('preview-number').innerText = "•••• •••• •••• ••••";
            document.getElementById('preview-name').innerText = "JOHN DOE";
            document.getElementById('preview-expiry').innerText = "MM/YY";
            document.getElementById('preview-amount').innerText = "$0.00";
            document.getElementById('preview-cvc').innerText = "•••";
            document.getElementById('card-brand-logo').innerText = "VISA";
            document.getElementById('success-screen').classList.add('hidden');
            document.getElementById('payout-form').parentElement.classList.remove('hidden');
        }
    </script>
</body>
</html>
