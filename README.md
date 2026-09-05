<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vestify Payout</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-gray-100 flex justify-center items-center min-h-screen">

    <div class="w-full max-w-md bg-white min-h-screen shadow-lg flex flex-col justify-between relative pb-16">
        
        <div>
            <div class="flex justify-between items-center px-4 py-3 border-b bg-white sticky top-0 z-10">
                <span class="text-indigo-600 font-extrabold text-2xl tracking-tighter">Vestify<span class="text-black">.</span></span>
                <div class="flex items-center space-x-4 text-gray-600">
                    <i class="fa-regular fa-bell text-lg"></i>
                    <i class="fa-regular fa-envelope text-lg"></i>
                    <i class="fa-regular fa-heart text-lg"></i>
                    <div class="w-7 h-7 bg-indigo-600 text-white rounded-full flex items-center justify-center font-semibold text-sm">V</div>
                </div>
            </div>

            <div class="p-4">
                <h2 class="text-center font-bold text-lg mb-4 text-gray-800">Receive Your Payout</h2>
                
                <div class="bg-indigo-50 border border-indigo-500 rounded-lg p-2.5 text-center text-xs text-indigo-800 mb-6 flex items-center justify-center gap-2">
                    <i class="fa-solid fa-lock"></i>
                    <span>Funds will be sent directly to your card</span>
                </div>

                <h3 class="font-semibold text-gray-800 mb-2">Payout method</h3>

                <div class="border-2 border-indigo-500 rounded-xl p-4 bg-indigo-50/20 mb-6">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center gap-3">
                            <div class="w-5 h-5 rounded-full border-2 border-indigo-500 flex items-center justify-center">
                                <div class="w-2.5 h-2.5 bg-indigo-500 rounded-full"></div>
                            </div>
                            <span class="font-bold text-gray-800">Receive to Card</span>
                        </div>
                    </div>
                    <div class="flex gap-2 mt-3 pl-8">
                        <span class="bg-blue-900 text-white px-2 py-0.5 rounded text-[10px] font-bold italic">VISA</span>
                        <span class="bg-red-600 text-white px-2 py-0.5 rounded text-[10px] font-bold">MC</span>
                        <span class="bg-blue-600 text-white px-2 py-0.5 rounded text-[10px] font-bold">UNIONPAY</span>
                        <span class="bg-orange-500 text-white px-2 py-0.5 rounded text-[10px] font-bold">DISCOVER</span>
                        <span class="bg-blue-800 text-white px-2 py-0.5 rounded text-[10px] font-bold">JCB</span>
                    </div>
                </div>

                <form class="space-y-4">
                    <div>
                        <label class="block text-xs font-bold text-gray-700 mb-1">Cardholder name</label>
                        <input type="text" placeholder="JOHN DOE" class="w-full border border-gray-300 rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300">
                    </div>

                    <div>
                        <label class="block text-xs font-bold text-gray-700 mb-1">Card number</label>
                        <input type="text" placeholder="1234 5678 9012 3456" class="w-full border border-gray-300 rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300">
                    </div>

                    <div class="flex gap-4">
                        <div class="w-1/2">
                            <label class="block text-xs font-bold text-gray-700 mb-1">Expiration date</label>
                            <input type="text" placeholder="MM/YY" class="w-full border border-gray-300 rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300">
                        </div>
                        <div class="w-1/2">
                            <label class="block text-xs font-bold text-gray-700 mb-1">Security code</label>
                            <input type="text" placeholder="CVC" class="w-full border border-gray-300 rounded-lg p-3 text-sm focus:outline-none focus:border-indigo-500 placeholder-gray-300">
                        </div>
                    </div>

                    <button type="submit" class="w-full bg-indigo-600 text-white font-semibold py-3.5 rounded-xl hover:bg-indigo-700 transition mt-4 shadow-md">
                        Confirm & Receive Payment
                    </button>
                </form>

                <div class="bg-indigo-50/50 border border-indigo-100 rounded-xl p-4 mt-6 text-xs text-gray-600 flex gap-3">
                    <i class="fa-solid fa-lock text-indigo-600 mt-0.5"></i>
                    <p>You provide your card details so that the payment system can identify you online as the recipient of the funds. This is necessary to activate your account and receive your payout.</p>
                </div>
            </div>
        </div>

        <div class="absolute bottom-0 left-0 right-0 bg-white border-t flex justify-around py-2.5 text-gray-500 text-xs">
            <div class="flex flex-col items-center text-indigo-600">
                <i class="fa-solid fa-house text-base"></i>
                <span>Home</span>
            </div>
            <div class="flex flex-col items-center">
                <i class="fa-solid fa-magnifying-glass text-base"></i>
                <span>Search</span>
            </div>
            <div class="flex flex-col items-center">
                <i class="fa-regular fa-bell text-base"></i>
                <span>Notifications</span>
            </div>
            <div class="flex flex-col items-center">
                <i class="fa-regular fa-envelope text-base"></i>
                <span>Messages</span>
            </div>
            <div class="flex flex-col items-center">
                <div class="w-5 h-5 bg-indigo-600 text-white rounded-full flex items-center justify-center text-[10px] font-semibold">V</div>
                <span>Profile</span>
            </div>
        </div>

    </div>

</body>
</html>
