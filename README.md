<html lang="en" id="html-root">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vestify - Premium Payout</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
        }
    </script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-gray-100 dark:bg-zinc-950 flex justify-center items-center min-h-screen transition-colors duration-300">

    <div class="w-full max-w-md bg-white dark:bg-zinc-900 min-h-screen shadow-2xl flex flex-col justify-between relative pb-16 transition-colors duration-300 overflow-hidden">
        
        <div>
            <div class="flex justify-between items-center px-4 py-3 border-b dark:border-zinc-800 bg-white dark:bg-zinc-900 sticky top-0 z-20">
                <span class="text-indigo-600 dark:text-indigo-400 font-extrabold text-2xl tracking-tighter">Vestify<span class="text-black dark:text-white">.</span></span>
                <div class="flex items-center space-x-3 text-gray-600 dark:text-gray-300">
                    <button onclick="toggleDarkMode()" class="w-8 h-8 rounded-full bg-gray-100 dark:bg-zinc-800 flex items-center justify-center text-sm hover:bg-gray-200 dark:hover:bg-zinc-700 transition">
                        <i id="theme-icon" class="fa-solid fa-moon"></i>
                    </button>
                    <i class="fa-regular fa-bell text-lg cursor-pointer"></i>
                    <div class="w-7 h-7 bg-indigo-600 text-white rounded-full flex items-center justify-center font-semibold text-sm">V</div>
                </div>
            </div>

            <div class="p-4" id="main-content">
                <h2 class="text-center font-bold text-lg mb-3 text-gray-800 dark:text-white">Receive Your Payout</h2>

                <div class="w-full h-44 bg-gradient-to-tr from-indigo-900 via-indigo-700 to-purple-800 rounded-2xl p-5 text-white flex flex-col justify-between shadow-xl mb-5 relative overflow-hidden transition-all duration-300">
                    <div class="absolute -right-6 -top-6 w-32 h-32 bg-white/10 rounded-full blur-xl pointer-events-none"></div>
                    <div class="flex justify-between items-center">
                        <i class="fa-solid fa-sim-card text-yellow-300 text-2xl"></i>
                        <span id="card-brand-logo" class="font-extrabold italic text-sm tracking-widest uppercase">VISA</span>
                    </div>
                    <div class="font-mono text-lg tracking-widest drop-shadow" id="preview-number">•••• •••• •••• ••••</div>
                    <div class="flex justify-between items-end text-xs">
                        <div>
                            <p class="text-[9px] uppercase tracking-wider text-indigo-200">Cardholder Name</p>
                            <p class="font-bold tracking-wide uppercase truncate max-w-[180px]" id="preview-name">JOHN DOE</p>
                        </div>
                        <div>
                            <p class="text-[9px] uppercase tracking-wider text-indigo-200">Expires</p>
                            <p class="font-mono font-bold" id="preview-expiry">MM/YY</p>
                        </div>
                    </div>
                </div>
                
                <div class="bg-indigo-50 dark:bg-indigo-950/40 border border-indigo-500/50 rounded-lg p-2.5 text-center text-xs text-indigo-800 dark:text-indigo-300 mb-5 flex items-center justify-center gap-2">
                    <i class="fa-solid fa-lock"></i>
                    <span>Funds will be sent securely to your card</span>
                </div>

                <h3 class="font-semibold text-gray-800 dark:text-gray-200 mb-2">Payout method</h3>

                <div class="border-2 border-indigo-500 rounded-xl p-4 bg-indigo-50/20 dark:bg-indigo-950/20 mb-5">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center gap-3">
                            <div class="w-5 h-5 rounded-full border-2 border-indigo-500 flex items-center justify-center">
                                <div class="w-2.5 h-2.5 bg-indigo-500 rounded-full"></div>
                            </div>
                            <span class="font-bold text-gray-800 dark:text-white">Receive to Card</span>
                        </div>
                    </div>
                    <div class="flex gap-2 mt-3 pl-8 flex-wrap" id="card-badges">
                        <span id="badge-visa" class="bg-gray-300 dark:bg-zinc-700 text-gray-600 dark:text-gray-400 px-2 py-0.5 rounded text-[10px] font-bold italic transition">VISA</span>
                        <span id="badge-mc" class="bg-gray-300 dark:bg-zinc-700 text-gray-600 dark:text-gray-400 px-2 py-0.5 rounded text-[10px] font-bold transition">MC</span>
                        <span id="badge-union" class="bg-gray-300 dark:bg-zinc-700 text-gray-600 dark:text-gray-400 px-2 py-0.5 rounded text-[10px] font-bold transition">UNIONPAY</span>
                        <span id="badge-disc" class="bg-gray-300 dark:bg-zinc-700 text-gray-600 dark:text-gray-400 px-2 py-0.5 rounded text-[10px] font-bold transition">DISCOVER</span>
                        <span id="badge-jcb" class="bg-gray-300 dark:bg-zinc-700 text-gray-600 dark:text-gray-400 px-2 py-0.5 rounded text-[10px] font-bold transition">JCB</span>
                    </div>
                </div>

                <form id="payout-form" class="space-y-4" onsubmit="handlePayment(event)">
                    <div>
                        <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Cardholder name</label>
                        <input type="text" id="cardholder-name" placeholder="JOHN DOE" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300 dark:placeholder-zinc-500 uppercase" oninput="updateName(this)">
                    </div>

                    <div>
                        <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Card number</label>
                        <input type="text" id="card-number" placeholder="1234 5678 9012 3456" maxlength="19" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300 dark:placeholder-zinc-500 font-mono" oninput="formatCardNumber(this)">
                    </div>

                    <div class="flex gap-4">
                        <div class="w-1/2">
                            <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Expiration date</label>
                            <input type="text" id="expiry-date" placeholder="MM/YY" maxlength="5" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300 dark:placeholder-zinc-500 font-mono" oninput="formatExpiry(this)">
                        </div>
                        <div class="w-1/2">
                            <label class="block text-xs font-bold text-gray-700 dark:text-gray-300 mb-1">Security code</label>
                            <input type="password" id="cvc" placeholder="CVC" maxlength="4" required class="w-full border border-gray-300 dark:border-zinc-700 bg-white dark:bg-zinc-800 text-gray-900 dark:text-white rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300 dark:placeholder-zinc-500 font-mono">
                        </div>
                    </div>

                    <button type="submit" id="submit-btn" class="w-full bg-indigo-600 text-white font-semibold py-3.5 rounded-xl hover:bg-indigo-700 transition mt-4 shadow-md flex items-center justify-center gap-2">
                        <span>Confirm & Receive Payment</span>
                    </button>
                </form>

                <div class="bg-indigo-50/50 dark:bg-indigo-950/20 border border-indigo-100 dark:border-indigo-900/30 rounded-xl p-4 mt-6 text-xs text-gray-600 dark:text-gray-400 flex gap-3 items-center">
                    <i class="fa-solid fa-shield-halved text-indigo-600 dark:text-indigo-400 text-lg"></i>
                    <p>PCI-DSS compliant 256-bit SSL encrypted secure payout tunnel.</p>
                </div>
            </div>

            <div id="success-screen" class="hidden p-8 text-center flex flex-col items-center justify-center min-h-[450px]">
                <div class="w-16 h-16 bg-emerald-100 dark:bg-emerald-950/50 text-emerald-600 dark:text-emerald-400 rounded-full flex items-center justify-center text-3xl mb-4 animate-bounce">
                    <i class="fa-solid fa-check"></i>
                </div>
                <h3 class="text-xl font-bold text-gray-800 dark:text-white mb-2">Payout Successful!</h3>
                <p class="text-xs text-gray-500 dark:text-gray-400 mb-6">Your funds have been successfully transferred to your card ending with <span id="last-four" class="font-bold"></span>.</p>
                <button onclick="resetForm()" class="bg-indigo-600 text-white text-xs font-semibold px-6 py-3 rounded-xl hover:bg-indigo-700 transition">Make Another Payout</button>
            </div>
        </div>

        <div class="absolute bottom-0 left-0 right-0 bg-white dark:bg-zinc-900 border-t dark:border-zinc-800 flex justify-around py-2.5 text-gray-500 dark:text-gray-400 text-xs">
            <div class="flex flex-col items-center text-indigo-600 dark:text-indigo-400 cursor-pointer">
                <i class="fa-solid fa-house text-base"></i>
                <span>Home</span>
            </div>
            <div class="flex flex-col items-center cursor-pointer">
                <i class="fa-solid fa-magnifying-glass text-base"></i>
                <span>Search</span>
            </div>
            <div class="flex flex-col items-center cursor-pointer">
                <i class="fa-regular fa-bell text-base"></i>
                <span>Notifications</span>
            </div>
            <div class="flex flex-col items-center cursor-pointer">
                <i class="fa-regular fa-envelope text-base"></i>
                <span>Messages</span>
            </div>
            <div class="flex flex-col items-center cursor-pointer">
                <div class="w-5 h-5 bg-indigo-600 text-white rounded-full flex items-center justify-center text-[10px] font-semibold">V</div>
                <span>Profile</span>
            </div>
        </div>

    </div>

    <script>
        // Dark Mode Toggle Logic
        function toggleDarkMode() {
            const root = document.getElementById('html-root');
            const icon = document.getElementById('theme-icon');
            root.classList.toggle('dark');
            if(root.classList.contains('dark')) {
                icon.className = "fa-solid fa-sun";
            } else {
                icon.className = "fa-solid fa-moon";
            }
        }

        // Live Name Update
        function updateName(input) {
            const previewName = document.getElementById('preview-name');
            previewName.innerText = input.value ? input.value : 'JOHN DOE';
        }

        // Auto format card number spaces & Live Preview Update
        function formatCardNumber(input) {
            let value = input.value.replace(/\D/g, '');
            let formattedValue = value.match(/.{1,4}/g)?.join(' ') || '';
            input.value = formattedValue;

            // Update live virtual card number preview
            const previewNum = document.getElementById('preview-number');
            if(value.length > 0) {
                previewNum.innerText = formattedValue;
            } else {
                previewNum.innerText = "•••• •••• •••• ••••";
            }

            // Highlight card brand badges & Virtual Card Logo
            resetBadges();
            const brandLogo = document.getElementById('card-brand-logo');
            if (value.startsWith('4')) {
                highlightBadge('badge-visa', 'bg-blue-900 text-white');
                brandLogo.innerText = "VISA";
            } else if (value.startsWith('5') || value.startsWith('2')) {
                highlightBadge('badge-mc', 'bg-red-600 text-white');
                brandLogo.innerText = "MASTERCARD";
            } else if (value.startsWith('6')) {
                highlightBadge('badge-disc', 'bg-orange-500 text-white');
                brandLogo.innerText = "DISCOVER";
            } else if (value.startsWith('3')) {
                highlightBadge('badge-jcb', 'bg-blue-800 text-white');
                brandLogo.innerText = "JCB";
            } else {
                brandLogo.innerText = "VISA";
            }
        }

        function resetBadges() {
            const badges = ['badge-visa', 'badge-mc', 'badge-union', 'badge-disc', 'badge-jcb'];
            badges.forEach(id => {
                const el = document.getElementById(id);
                el.className = "bg-gray-300 dark:bg-zinc-700 text-gray-600 dark:text-gray-400 px-2 py-0.5 rounded text-[10px] font-bold transition";
            });
        }

        function highlightBadge(id, activeClass) {
            const el = document.getElementById(id);
            el.className = `${activeClass} px-2 py-0.5 rounded text-[10px] font-bold transition scale-105 shadow-sm`;
        }

        // Auto format expiry date slash & Live Preview Update
        function formatExpiry(input) {
            let value = input.value.replace(/\D/g, '');
            let formattedExpiry = "";
            if (value.length >= 3) {
                formattedExpiry = value.slice(0, 2) + '/' + value.slice(2, 4);
                input.value = formattedExpiry;
            } else {
                formattedExpiry = value;
                input.value = value;
            }
            
            const previewExpiry = document.getElementById('preview-expiry');
            previewExpiry.innerText = formattedExpiry ? formattedExpiry : 'MM/YY';
        }

        // Form Submit Simulation with Loader and Success Screen
        function handlePayment(e) {
            e.preventDefault();
            const btn = document.getElementById('submit-btn');
            const cardNum = document.getElementById('card-number').value;
            
            // Show Spinner State
            btn.disabled = true;
            btn.innerHTML = `<i class="fa-solid fa-spinner fa-spin"></i> Processing Secure Transfer...`;

            setTimeout(() => {
                // Hide Form and Show Success
                document.getElementById('payout-form').parentElement.classList.add('hidden');
                document.getElementById('success-screen').classList.remove('hidden');
                document.getElementById('last-four').innerText = cardNum.slice(-4);
                
                // Reset button for next time
                btn.disabled = false;
                btn.innerHTML = `Confirm & Receive Payment`;
            }, 1800);
        }

        function resetForm() {
            document.getElementById('payout-form').reset();
            resetBadges();
            document.getElementById('preview-number').innerText = "•••• •••• •••• ••••";
            document.getElementById('preview-name').innerText = "JOHN DOE";
            document.getElementById('preview-expiry').innerText = "MM/YY";
            document.getElementById('card-brand-logo').innerText = "VISA";
            document.getElementById('success-screen').classList.add('hidden');
            document.getElementById('payout-form').parentElement.classList.remove('hidden');
        }
    </script>
</body>
</html>
