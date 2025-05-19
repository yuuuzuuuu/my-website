<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Finance Tracker</title>
<script src="https://cdn.tailwindcss.com/3.4.16"></script>
<script>tailwind.config={theme:{extend:{colors:{primary:'#4F46E5',secondary:'#10B981'},borderRadius:{'none':'0px','sm':'4px',DEFAULT:'8px','md':'12px','lg':'16px','xl':'20px','2xl':'24px','3xl':'32px','full':'9999px','button':'8px'}}}}</script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css">
<style>
:where([class^="ri-"])::before { content: "\f3c2"; }
body {
font-family: 'Inter', sans-serif;
background-color: #F9FAFB;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
-webkit-appearance: none;
margin: 0;
}
.progress-ring {
transform: rotate(-90deg);
}
.progress-ring-circle {
transition: stroke-dashoffset 0.35s;
transform-origin: 50% 50%;
}
.switch {
position: relative;
display: inline-block;
width: 46px;
height: 24px;
}
.switch input {
opacity: 0;
width: 0;
height: 0;
}
.slider {
position: absolute;
cursor: pointer;
top: 0;
left: 0;
right: 0;
bottom: 0;
background-color: #e5e7eb;
transition: .4s;
border-radius: 24px;
}
.slider:before {
position: absolute;
content: "";
height: 18px;
width: 18px;
left: 3px;
bottom: 3px;
background-color: white;
transition: .4s;
border-radius: 50%;
}
input:checked + .slider {
background-color: #4F46E5;
}
input:checked + .slider:before {
transform: translateX(22px);
}
</style>
</head>
<body>
<div class="min-h-screen flex flex-col">
<!-- Header -->
<header class="bg-white shadow-sm">
<div class="container mx-auto px-4 py-4 flex justify-between items-center">
<div class="flex items-center">
<h1 class="text-2xl font-['Pacifico'] text-primary">logo</h1>
</div>
<div class="flex items-center space-x-4">
<div class="w-10 h-10 flex items-center justify-center bg-gray-100 rounded-full text-gray-600 cursor-pointer relative" id="notification-bell">
<i class="ri-notification-3-line"></i>
<span class="absolute -top-1 -right-1 bg-red-500 text-white text-xs w-5 h-5 flex items-center justify-center rounded-full">3</span>
<div id="notification-panel" class="absolute right-0 top-12 w-80 bg-white rounded-lg shadow-lg z-10 hidden">
<div class="p-4 border-b border-gray-100">
<div class="flex justify-between items-center">
<h3 class="font-medium text-gray-800">Notifications</h3>
<button id="mark-all-read" class="text-sm text-primary hover:underline">Mark all as read</button>
</div>
</div>
<div class="max-h-96 overflow-y-auto">
<div class="p-4 border-b border-gray-100 bg-blue-50">
<div class="flex">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full text-blue-600 mr-3 flex-shrink-0">
<i class="ri-information-line"></i>
</div>
<div>
<p class="text-sm text-gray-800">Your monthly spending report is ready to view.</p>
<p class="text-xs text-gray-500 mt-1">10 minutes ago</p>
</div>
</div>
</div>
<div class="p-4 border-b border-gray-100 bg-blue-50">
<div class="flex">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full text-green-600 mr-3 flex-shrink-0">
<i class="ri-check-line"></i>
</div>
<div>
<p class="text-sm text-gray-800">Successfully saved $250 to your emergency fund.</p>
<p class="text-xs text-gray-500 mt-1">2 hours ago</p>
</div>
</div>
</div>
<div class="p-4 border-b border-gray-100 bg-blue-50">
<div class="flex">
<div class="w-8 h-8 flex items-center justify-center bg-yellow-100 rounded-full text-yellow-600 mr-3 flex-shrink-0">
<i class="ri-alert-line"></i>
</div>
<div>
<p class="text-sm text-gray-800">You're approaching your shopping budget limit.</p>
<p class="text-xs text-gray-500 mt-1">Yesterday</p>
</div>
</div>
</div>
<div class="p-4 border-b border-gray-100">
<div class="flex">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full text-purple-600 mr-3 flex-shrink-0">
<i class="ri-gift-line"></i>
</div>
<div>
<p class="text-sm text-gray-800">Earn 2x points on all purchases this weekend!</p>
<p class="text-xs text-gray-500 mt-1">2 days ago</p>
</div>
</div>
</div>
<div class="p-4 border-b border-gray-100">
<div class="flex">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full text-red-600 mr-3 flex-shrink-0">
<i class="ri-error-warning-line"></i>
</div>
<div>
<p class="text-sm text-gray-800">Unusual transaction detected on your account.</p>
<p class="text-xs text-gray-500 mt-1">3 days ago</p>
</div>
</div>
</div>
</div>
<div class="p-3 text-center border-t border-gray-100">
<a href="#" class="text-sm text-primary hover:underline">View all notifications</a>
</div>
</div>
</div>
<div class="w-10 h-10 flex items-center justify-center bg-gray-100 rounded-full text-gray-600 cursor-pointer relative" id="settings-button">
<i class="ri-settings-3-line"></i>
<div id="settings-panel" class="absolute right-0 top-12 w-64 bg-white rounded-lg shadow-lg z-10 hidden">
<div class="py-2">
<a href="https://readdy.ai/home/d2012e10-e039-4d99-9e7c-25344199fe18/76f9a572-3b07-471d-8329-c1526eb3b029" data-readdy="true" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
<div class="w-5 h-5 flex items-center justify-center mr-3 text-gray-500">
<i class="ri-user-settings-line"></i>
</div>
<span>Account Settings</span>
</a>
<a href="#" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
<div class="w-5 h-5 flex items-center justify-center mr-3 text-gray-500">
<i class="ri-notification-4-line"></i>
</div>
<span>Notification Preferences</span>
</a>
<a href="#" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
<div class="w-5 h-5 flex items-center justify-center mr-3 text-gray-500">
<i class="ri-exchange-dollar-line"></i>
</div>
<span>Currency Settings</span>
</a>
<a href="#" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
<div class="w-5 h-5 flex items-center justify-center mr-3 text-gray-500">
<i class="ri-palette-line"></i>
</div>
<span>Theme Options</span>
</a>
<a href="#" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
<div class="w-5 h-5 flex items-center justify-center mr-3 text-gray-500">
<i class="ri-shield-keyhole-line"></i>
</div>
<span>Security Settings</span>
</a>
<a href="#" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
<div class="w-5 h-5 flex items-center justify-center mr-3 text-gray-500">
<i class="ri-question-line"></i>
</div>
<span>Help & Support</span>
</a>
</div>
</div>
</div>
<div class="w-10 h-10 bg-gray-200 rounded-full overflow-hidden">
<img src="https://public.readdy.ai/ai/img_res/f62b1d660cfe9783d26aa9d90bdbd883.jpg" alt="Profile" class="w-full h-full object-cover">
</div>
</div>
</div>
</header>
<!-- Main Content -->
<main class="flex-grow container mx-auto px-4 py-6">
<!-- Balance Overview -->
<div class="bg-white rounded-lg shadow-sm p-6 mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="text-lg font-medium text-gray-800">Total Balance</h2>
<div class="flex items-center space-x-2 bg-gray-100 rounded-full px-3 py-1">
<span class="text-sm text-gray-600">April 2025</span>
<div class="w-5 h-5 flex items-center justify-center text-gray-600">
<i class="ri-arrow-down-s-line"></i>
</div>
</div>
</div>
<div class="flex justify-between items-end mb-6">
<div>
<p class="text-3xl font-bold text-gray-900">$4,285.65</p>
<p class="text-sm text-green-600 flex items-center mt-1">
<span class="w-4 h-4 flex items-center justify-center mr-1">
<i class="ri-arrow-up-line"></i>
</span>
<span>12.5% from last month</span>
</p>
</div>
<div class="flex space-x-3">
<button id="add-income-btn" class="bg-primary text-white px-4 py-2 !rounded-button flex items-center whitespace-nowrap">
<span class="w-5 h-5 flex items-center justify-center mr-1">
<i class="ri-add-line"></i>
</span>
<span>Add Income</span>
</button>
<button class="bg-white border border-gray-300 text-gray-700 px-4 py-2 !rounded-button flex items-center whitespace-nowrap">
<span class="w-5 h-5 flex items-center justify-center mr-1">
<i class="ri-subtract-line"></i>
</span>
<span>Add Expense</span>
</button>
</div>
</div>
<div class="grid grid-cols-3 gap-4">
<div class="bg-gray-50 rounded p-4">
<div class="flex items-center mb-2">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full text-blue-600 mr-2">
<i class="ri-arrow-down-line"></i>
</div>
<span class="text-sm text-gray-600">Income</span>
</div>
<p class="text-xl font-semibold text-gray-900">$6,240.00</p>
</div>
<div class="bg-gray-50 rounded p-4">
<div class="flex items-center mb-2">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full text-red-600 mr-2">
<i class="ri-arrow-up-line"></i>
</div>
<span class="text-sm text-gray-600">Expenses</span>
</div>
<p class="text-xl font-semibold text-gray-900">$1,954.35</p>
</div>
<div class="bg-gray-50 rounded p-4">
<div class="flex items-center mb-2">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full text-purple-600 mr-2">
<i class="ri-wallet-3-line"></i>
</div>
<span class="text-sm text-gray-600">Savings</span>
</div>
<p class="text-xl font-semibold text-gray-900">$2,135.65</p>
</div>
</div>
</div>
<!-- Budget Progress -->
<div class="bg-white rounded-lg shadow-sm p-6 mb-6">
<div class="flex justify-between items-center mb-6">
<h2 class="text-lg font-medium text-gray-800">Budget Progress</h2>
<button class="text-primary text-sm font-medium flex items-center whitespace-nowrap">
<span>View All</span>
<span class="w-4 h-4 flex items-center justify-center ml-1">
<i class="ri-arrow-right-s-line"></i>
</span>
</button>
</div>
<div class="grid grid-cols-3 gap-6">
<div class="flex flex-col items-center">
<div class="relative w-32 h-32 mb-3">
<svg class="progress-ring" width="128" height="128">
<circle class="progress-ring-circle" stroke="#E5E7EB" stroke-width="8" fill="transparent" r="56" cx="64" cy="64"/>
<circle class="progress-ring-circle" stroke="#4F46E5" stroke-width="8" fill="transparent" r="56" cx="64" cy="64" stroke-dasharray="351.86" stroke-dashoffset="88"/>
</svg>
<div class="absolute inset-0 flex flex-col items-center justify-center">
<span class="text-2xl font-bold text-gray-900">75%</span>
<span class="text-xs text-gray-500">used</span>
</div>
</div>
<h3 class="text-base font-medium text-gray-800">Food & Dining</h3>
<p class="text-sm text-gray-600">$450 / $600</p>
</div>
<div class="flex flex-col items-center">
<div class="relative w-32 h-32 mb-3">
<svg class="progress-ring" width="128" height="128">
<circle class="progress-ring-circle" stroke="#E5E7EB" stroke-width="8" fill="transparent" r="56" cx="64" cy="64"/>
<circle class="progress-ring-circle" stroke="#FBBF72" stroke-width="8" fill="transparent" r="56" cx="64" cy="64" stroke-dasharray="351.86" stroke-dashoffset="140.74"/>
</svg>
<div class="absolute inset-0 flex flex-col items-center justify-center">
<span class="text-2xl font-bold text-gray-900">60%</span>
<span class="text-xs text-gray-500">used</span>
</div>
</div>
<h3 class="text-base font-medium text-gray-800">Transportation</h3>
<p class="text-sm text-gray-600">$180 / $300</p>
</div>
<div class="flex flex-col items-center">
<div class="relative w-32 h-32 mb-3">
<svg class="progress-ring" width="128" height="128">
<circle class="progress-ring-circle" stroke="#E5E7EB" stroke-width="8" fill="transparent" r="56" cx="64" cy="64"/>
<circle class="progress-ring-circle" stroke="#FC8D62" stroke-width="8" fill="transparent" r="56" cx="64" cy="64" stroke-dasharray="351.86" stroke-dashoffset="70.37"/>
</svg>
<div class="absolute inset-0 flex flex-col items-center justify-center">
<span class="text-2xl font-bold text-gray-900">80%</span>
<span class="text-xs text-gray-500">used</span>
</div>
</div>
<h3 class="text-base font-medium text-gray-800">Shopping</h3>
<p class="text-sm text-gray-600">$320 / $400</p>
</div>
</div>
</div>
<!-- Recent Transactions -->
<div class="bg-white rounded-lg shadow-sm p-6 mb-6">
<div class="flex justify-between items-center mb-6">
<h2 class="text-lg font-medium text-gray-800">Recent Transactions</h2>
<div class="flex items-center">
<div class="flex items-center bg-gray-100 rounded-full px-1 py-1 mr-3">
<button class="px-3 py-1 bg-white rounded-full text-sm font-medium text-gray-700 shadow-sm">All</button>
<button class="px-3 py-1 text-sm font-medium text-gray-600">Income</button>
<button class="px-3 py-1 text-sm font-medium text-gray-600">Expense</button>
</div>
<button class="text-primary text-sm font-medium flex items-center whitespace-nowrap">
<span>View All</span>
<span class="w-4 h-4 flex items-center justify-center ml-1">
<i class="ri-arrow-right-s-line"></i>
</span>
</button>
</div>
</div>
<div class="space-y-4">
<div class="flex items-center justify-between p-3 rounded-lg hover:bg-gray-50 transition">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-blue-100 rounded-full text-blue-600 mr-3">
<i class="ri-building-line"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Salary Deposit</h3>
<p class="text-sm text-gray-500">April 1, 2025</p>
</div>
</div>
<span class="text-base font-medium text-green-600">+$3,250.00</span>
</div>
<div class="flex items-center justify-between p-3 rounded-lg hover:bg-gray-50 transition">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-red-100 rounded-full text-red-600 mr-3">
<i class="ri-shopping-bag-line"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Whole Foods Market</h3>
<p class="text-sm text-gray-500">April 1, 2025</p>
</div>
</div>
<span class="text-base font-medium text-red-600">-$85.32</span>
</div>
<div class="flex items-center justify-between p-3 rounded-lg hover:bg-gray-50 transition">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-red-100 rounded-full text-red-600 mr-3">
<i class="ri-netflix-fill"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Netflix Subscription</h3>
<p class="text-sm text-gray-500">March 31, 2025</p>
</div>
</div>
<span class="text-base font-medium text-red-600">-$15.99</span>
</div>
<div class="flex items-center justify-between p-3 rounded-lg hover:bg-gray-50 transition">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-red-100 rounded-full text-red-600 mr-3">
<i class="ri-restaurant-line"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Shake Shack</h3>
<p class="text-sm text-gray-500">March 30, 2025</p>
</div>
</div>
<span class="text-base font-medium text-red-600">-$32.48</span>
</div>
<div class="flex items-center justify-between p-3 rounded-lg hover:bg-gray-50 transition">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-red-100 rounded-full text-red-600 mr-3">
<i class="ri-taxi-line"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Uber Ride</h3>
<p class="text-sm text-gray-500">March 29, 2025</p>
</div>
</div>
<span class="text-base font-medium text-red-600">-$24.75</span>
</div>
</div>
</div>
<!-- Spending Limits -->
<div class="bg-white rounded-lg shadow-sm p-6">
<div class="flex justify-between items-center mb-6">
<h2 class="text-lg font-medium text-gray-800">Spending Limits</h2>
<button class="bg-primary text-white px-4 py-2 !rounded-button flex items-center whitespace-nowrap">
<span class="w-5 h-5 flex items-center justify-center mr-1">
<i class="ri-add-line"></i>
</span>
<span>Add Limit</span>
</button>
</div>
<div class="space-y-5">
<div class="flex items-center justify-between">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-purple-100 rounded-full text-purple-600 mr-3">
<i class="ri-shopping-bag-line"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Shopping</h3>
<div class="w-full bg-gray-200 rounded-full h-2 mt-1">
<div class="bg-primary h-2 rounded-full" style="width: 80%"></div>
</div>
</div>
</div>
<div class="flex items-center">
<div class="mr-6">
<p class="text-sm text-gray-500">Limit</p>
<p class="text-base font-medium text-gray-800">$400 / month</p>
</div>
<label class="switch">
<input type="checkbox" checked>
<span class="slider"></span>
</label>
</div>
</div>
<div class="flex items-center justify-between">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-blue-100 rounded-full text-blue-600 mr-3">
<i class="ri-restaurant-line"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Restaurants</h3>
<div class="w-full bg-gray-200 rounded-full h-2 mt-1">
<div class="bg-primary h-2 rounded-full" style="width: 65%"></div>
</div>
</div>
</div>
<div class="flex items-center">
<div class="mr-6">
<p class="text-sm text-gray-500">Limit</p>
<p class="text-base font-medium text-gray-800">$300 / month</p>
</div>
<label class="switch">
<input type="checkbox" checked>
<span class="slider"></span>
</label>
</div>
</div>
<div class="flex items-center justify-between">
<div class="flex items-center">
<div class="w-10 h-10 flex items-center justify-center bg-green-100 rounded-full text-green-600 mr-3">
<i class="ri-taxi-line"></i>
</div>
<div>
<h3 class="text-base font-medium text-gray-800">Transportation</h3>
<div class="w-full bg-gray-200 rounded-full h-2 mt-1">
<div class="bg-primary h-2 rounded-full" style="width: 40%"></div>
</div>
</div>
</div>
<div class="flex items-center">
<div class="mr-6">
<p class="text-sm text-gray-500">Limit</p>
<p class="text-base font-medium text-gray-800">$200 / month</p>
</div>
<label class="switch">
<input type="checkbox" checked>
<span class="slider"></span>
</label>
</div>
</div>
</div>
</div>
</main>
<!-- Bottom Navigation -->
<nav class="bg-white border-t border-gray-200 fixed bottom-0 w-full">
<div class="container mx-auto px-4">
<div class="flex justify-between items-center py-3">
<a href="#" class="flex flex-col items-center text-primary">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-home-5-line"></i>
</div>
<span class="text-xs mt-1">Home</span>
</a>
<a href="https://readdy.ai/home/d2012e10-e039-4d99-9e7c-25344199fe18/55f99368-f289-48cc-a93a-bc3108f85560" data-readdy="true" class="flex flex-col items-center text-gray-500">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-exchange-dollar-line"></i>
</div>
<span class="text-xs mt-1">Transactions</span>
</a>
<div class="relative -mt-5">
<button class="w-14 h-14 rounded-full bg-primary text-white flex items-center justify-center shadow-lg">
<i class="ri-add-line text-2xl"></i>
</button>
</div>
<a href="#" class="flex flex-col items-center text-gray-500">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-pie-chart-line"></i>
</div>
<span class="text-xs mt-1">Budget</span>
</a>
<a href="#" class="flex flex-col items-center text-gray-500">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-user-3-line"></i>
</div>
<span class="text-xs mt-1">Profile</span>
</a>
</div>
</div>
</nav>
</div>
<script>
document.addEventListener('DOMContentLoaded', function() {
// Toggle switches
const switches = document.querySelectorAll('.switch input');
switches.forEach(switchEl => {
switchEl.addEventListener('change', function() {
// Handle switch toggle
});
});
// Add transaction button
const addButton = document.querySelector('nav button');
addButton.addEventListener('click', function() {
// Show transaction form
});
// Notification panel functionality
const notificationBell = document.getElementById('notification-bell');
const notificationPanel = document.getElementById('notification-panel');
const markAllReadBtn = document.getElementById('mark-all-read');
// Toggle notification panel
notificationBell.addEventListener('click', function(e) {
e.stopPropagation();
notificationPanel.classList.toggle('hidden');
// Hide settings panel when notification panel is opened
document.getElementById('settings-panel').classList.add('hidden');
});
// Close notification panel when clicking outside
document.addEventListener('click', function(e) {
if (!notificationBell.contains(e.target)) {
notificationPanel.classList.add('hidden');
}
if (!document.getElementById('settings-button').contains(e.target)) {
document.getElementById('settings-panel').classList.add('hidden');
}
});
// Mark all as read
markAllReadBtn.addEventListener('click', function() {
const unreadNotifications = document.querySelectorAll('#notification-panel .bg-blue-50');
unreadNotifications.forEach(notification => {
notification.classList.remove('bg-blue-50');
});
// Remove notification counter
const counter = notificationBell.querySelector('span');
counter.textContent = '0';
counter.classList.add('hidden');
});
// Prevent panel close when clicking inside the panel
notificationPanel.addEventListener('click', function(e) {
e.stopPropagation();
});
// Settings panel functionality
const settingsButton = document.getElementById('settings-button');
const settingsPanel = document.getElementById('settings-panel');
// Toggle settings panel
settingsButton.addEventListener('click', function(e) {
e.stopPropagation();
settingsPanel.classList.toggle('hidden');
// Hide notification panel when settings panel is opened
notificationPanel.classList.add('hidden');
});
// Prevent panel close when clicking inside the panel
settingsPanel.addEventListener('click', function(e) {
e.stopPropagation();
});

// Add Income Modal Functionality
const addIncomeBtn = document.getElementById('add-income-btn');
const incomeModal = document.getElementById('income-modal');
const closeIncomeModal = document.getElementById('close-income-modal');
const cancelIncomeBtn = document.getElementById('cancel-income-btn');
const incomeForm = document.getElementById('income-form');

// Open income modal
addIncomeBtn.addEventListener('click', function() {
  incomeModal.classList.remove('hidden');
  document.body.classList.add('overflow-hidden');
});

// Close income modal functions
function closeModal() {
  incomeModal.classList.add('hidden');
  document.body.classList.remove('overflow-hidden');
  incomeForm.reset();
}

if (closeIncomeModal) closeIncomeModal.addEventListener('click', closeModal);
if (cancelIncomeBtn) cancelIncomeBtn.addEventListener('click', closeModal);

// Close modal when clicking outside
incomeModal.addEventListener('click', function(e) {
  if (e.target === incomeModal) {
    closeModal();
  }
});

// Prevent modal close when clicking inside the form
if (document.querySelector('.income-modal-content')) {
  document.querySelector('.income-modal-content').addEventListener('click', function(e) {
    e.stopPropagation();
  });
}

// Handle form submission
if (incomeForm) {
  incomeForm.addEventListener('submit', function(e) {
    e.preventDefault();
    
    // Get form values
    const amount = document.getElementById('income-amount').value;
    const source = document.getElementById('income-source').value;
    const date = document.getElementById('income-date').value;
    const description = document.getElementById('income-description').value;
    const category = document.getElementById('income-category').value;
    
    // Here you would typically save this data to your backend
    console.log('Income added:', { amount, source, date, description, category });
    
    // Show success message
    const successMessage = document.getElementById('success-message');
    successMessage.classList.remove('hidden');
    
    // Hide success message after 3 seconds
    setTimeout(() => {
      successMessage.classList.add('hidden');
      closeModal();
    }, 2000);
  });
}
});
</script>
<!-- Income Modal -->
<div id="income-modal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
  <div class="income-modal-content bg-white rounded-lg shadow-xl w-full max-w-md mx-4">
    <div class="p-6">
      <div class="flex justify-between items-center mb-6">
        <h2 class="text-xl font-semibold text-gray-800">Add Income</h2>
        <button id="close-income-modal" class="text-gray-500 hover:text-gray-700">
          <div class="w-6 h-6 flex items-center justify-center">
            <i class="ri-close-line"></i>
          </div>
        </button>
      </div>
      <form id="income-form">
        <div class="space-y-4">
          <div>
            <label for="income-amount" class="block text-sm font-medium text-gray-700 mb-1">Amount</label>
            <div class="relative">
              <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                <span class="text-gray-500">$</span>
              </div>
              <input type="number" id="income-amount" name="amount" class="pl-8 pr-4 py-2 w-full border border-gray-300 rounded focus:ring-primary focus:border-primary" placeholder="0.00" required step="0.01" min="0.01">
            </div>
          </div>
          <div>
            <label for="income-source" class="block text-sm font-medium text-gray-700 mb-1">Source</label>
            <select id="income-source" name="source" class="w-full border border-gray-300 rounded py-2 px-3 focus:ring-primary focus:border-primary pr-8">
              <option value="salary">Salary</option>
              <option value="freelance">Freelance</option>
              <option value="investment">Investment</option>
              <option value="gift">Gift</option>
              <option value="other">Other</option>
            </select>
          </div>
          <div>
            <label for="income-date" class="block text-sm font-medium text-gray-700 mb-1">Date</label>
            <input type="date" id="income-date" name="date" class="w-full border border-gray-300 rounded py-2 px-3 focus:ring-primary focus:border-primary" required value="2025-04-01">
          </div>
          <div>
            <label for="income-category" class="block text-sm font-medium text-gray-700 mb-1">Category</label>
            <select id="income-category" name="category" class="w-full border border-gray-300 rounded py-2 px-3 focus:ring-primary focus:border-primary pr-8">
              <option value="regular">Regular Income</option>
              <option value="bonus">Bonus</option>
              <option value="passive">Passive Income</option>
              <option value="side-hustle">Side Hustle</option>
              <option value="other">Other</option>
            </select>
          </div>
          <div>
            <label for="income-description" class="block text-sm font-medium text-gray-700 mb-1">Description (Optional)</label>
            <textarea id="income-description" name="description" rows="2" class="w-full border border-gray-300 rounded py-2 px-3 focus:ring-primary focus:border-primary" placeholder="Add notes about this income"></textarea>
          </div>
        </div>
        <div class="mt-6 flex justify-end space-x-3">
          <button type="button" id="cancel-income-btn" class="px-4 py-2 border border-gray-300 rounded-button text-gray-700 bg-white hover:bg-gray-50 whitespace-nowrap">Cancel</button>
          <button type="submit" class="px-4 py-2 bg-primary text-white rounded-button hover:bg-primary/90 whitespace-nowrap">Save Income</button>
        </div>
      </form>
      <!-- Success Message -->
      <div id="success-message" class="hidden mt-4 p-3 bg-green-100 text-green-700 rounded-md">
        <div class="flex items-center">
          <div class="w-5 h-5 flex items-center justify-center mr-2">
            <i class="ri-check-line"></i>
          </div>
          <span>Income successfully added!</span>
        </div>
      </div>
    </div>
  </div>
</div>
</body>
</html>
