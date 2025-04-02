<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Personal Finance</title>
<script src="https://cdn.tailwindcss.com/3.4.16"></script>
<script>tailwind.config={theme:{extend:{colors:{primary:'#10b981',secondary:'#f97316'},borderRadius:{'none':'0px','sm':'4px',DEFAULT:'8px','md':'12px','lg':'16px','xl':'20px','2xl':'24px','3xl':'32px','full':'9999px','button':'8px'}}}}</script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/remixicon/4.6.0/remixicon.min.css">
<style>
:where([class^="ri-"])::before { content: "\f3c2"; }
body {
max-width: 375px;
margin: 0 auto;
min-height: 100vh;
position: relative;
padding-bottom: 64px;
}
.progress-ring {
transform: rotate(-90deg);
}
.progress-ring__circle {
transition: stroke-dashoffset 0.35s;
transform-origin: 50% 50%;
}
.splash-screen {
position: fixed;
top: 100%;
left: 0;
width: 100%;
height: 100%;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
background: linear-gradient(135deg, #10b981, #059669);
z-index: 9999;
animation: fadeOut 1.5s ease 2s forwards;
}
@keyframes fadeOut {
0% { opacity: 1; }
100% { opacity: 0; visibility: hidden; }
}
.splash-logo {
animation: pulse 2s infinite;
}
@keyframes pulse {
0% { transform: scale(1); }
50% { transform: scale(1.05); }
100% { transform: scale(1); }
}
.modal-container {
animation: fadeIn 0.3s ease;
}
@keyframes fadeIn {
0% { opacity: 0; }
100% { opacity: 1; }
}
.modal-container > div {
animation: slideUp 0.3s ease;
}
@keyframes slideUp {
0% { transform: translateY(20px); opacity: 0; }
100% { transform: translateY(0); opacity: 1; }
}
</style>
</head>
<body class="bg-gray-50">
<!-- Splash Screen -->
<div class="splash-screen">
<div class="splash-logo mb-6">
<h1 class="text-5xl font-['Pacifico'] text-white">FinTrack</h1>
</div>
<div class="flex flex-col items-center">
<div class="w-16 h-16 flex items-center justify-center bg-white/20 rounded-full mb-4">
<i class="ri-wallet-3-line ri-2x text-white"></i>
</div>
<p class="text-white text-lg mb-8">Your Personal Finance Assistant</p>
<div class="w-16 h-1">
<div class="w-full h-full bg-white/30 rounded-full overflow-hidden">
<div class="h-full bg-white rounded-full animate-[progress_2s_ease-in-out]" style="width: 100%; animation: progress 2s ease-in-out forwards;"></div>
</div>
</div>
</div>
</div>
<!-- Nav Bar -->
<header class="fixed top-0 w-full bg-white z-50 px-4 py-3 flex justify-between items-center shadow-sm">
<h1 class="text-xl font-['Pacifico'] text-primary">FinTrack</h1>
<div class="flex items-center gap-4">
<div class="w-8 h-8 flex items-center justify-center relative">
<i class="ri-notification-3-line ri-lg"></i>
<span class="absolute top-0 right-0 w-2 h-2 bg-red-500 rounded-full"></span>
</div>
<div class="settings-container">
    <h2>Settings</h2>
    <div class="setting-option">
        <label for="categories">Manage Categories</label>
        <button id="editCategories">Edit</button>
    </div>
    <div class="setting-option">
        <label for="spendingLimit">Spending Limit</label>
        <input type="number" id="spendingLimit" placeholder="Enter limit">
    </div>
    <div class="setting-option">
        <label for="themeToggle">Dark Mode</label>
        <input type="checkbox" id="themeToggle">
    </div>
    <div class="setting-option">
        <label for="currency">Currency</label>
        <select id="currency">
            <option value="USD">USD ($)</option>
            <option value="EUR">EUR (€)</option>
            <option value="IDR">IDR (Rp)</option>
        </select>
    </div>
    <div class="setting-option">
        <label for="settingsIcon">Settings</label>
        <i class="ri-settings-3-line ri-lg"></i>
    </div>
</div>
</header>
<!-- Main Content -->
<main class="pt-16 pb-16 px-4">
<!-- Balance Summary -->
<section class="mb-6 mt-4">
<div class="flex justify-between items-center mb-2">
<h2 class="text-sm text-gray-500">Total Balance</h2>
<div class="text-xs text-gray-500 bg-gray-100 px-2 py-1 rounded-full">April 2025</div>
</div>
<div class="flex justify-between items-end mb-2">
<h3 class="text-2xl font-bold">$4,285.65</h3>
<div class="flex items-center text-xs text-green-500">
<i class="ri-arrow-up-line ri-sm mr-1"></i>
<span>+2.5% from last month</span>
</div>
</div>
<div class="flex gap-2 mt-4">
<button class="flex-1 bg-primary text-white py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addIncomeBtn">
<i class="ri-add-line ri-lg mr-1"></i>
<span>Add Income</span>
</button>
<button class="flex-1 bg-white border border-gray-200 text-gray-700 py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addExpenseBtn">
<i class="ri-subtract-line ri-lg mr-1"></i>
<span>Add Expense</span>
</button>
</div>
</section>
<!-- Financial Overview -->
<section class="mb-6">
<div class="grid grid-cols-3 gap-3">
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mb-2">
<i class="ri-wallet-3-line text-blue-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Income</div>
<div class="font-semibold text-sm">$6,240.00</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mb-2">
<i class="ri-shopping-bag-line text-red-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Expenses</div>
<div class="font-semibold text-sm">$1,954.35</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mb-2">
<i class="ri-bank-line text-purple-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Savings</div>
<div class="font-semibold text-sm">$2,135.65</div>
</div>
</div>
</section>
<!-- Budget Progress -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Budget Progress</h2>
<a href="#" class="text-xs text-primary flex items-center cursor-pointer" id="viewAllBudgetBtn">
View All
<i class="ri-arrow-right-s-line ri-sm ml-1"></i>
</a>
</div>
<div class="grid grid-cols-3 gap-3">
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#6366f1" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="44"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">75%</div>
</div>
<div class="text-xs text-center">Food & Dining</div>
<div class="text-xs text-gray-500 mt-1">$450 / $600</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="70.4"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">60%</div>
</div>
<div class="text-xs text-center">Transportation</div>
<div class="text-xs text-gray-500 mt-1">$180 / $300</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="35.2"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">80%</div>
</div>
<div class="text-xs text-center">Shopping</div>
<div class="text-xs text-gray-500 mt-1">$320 / $400</div>
</div>
</div>
</section>
<!-- Recent Transactions -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Recent Transactions</h2>
<div class="flex gap-2">
<button class="text-xs bg-primary text-white px-2 py-1 rounded-full cursor-pointer" id="filterAll">All</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterIncome">Income</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterExpense">Expense</button>
</div>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-bank-card-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Salary Deposit</div>
<div class="text-xs text-gray-500">April 1, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$3,250.00</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-shopping-basket-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Whole Foods Market</div>
<div class="text-xs text-gray-500">April 3, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$85.32</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-netflex-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Netflix Subscription</div>
<div class="text-xs text-gray-500">March 31, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$15.99</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-funds-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Stock Dividend</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$125.50</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-restaurant-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shake Shack</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$32.48</div>
</div>
<div class="p-3 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-taxi-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Uber Ride</div>
<div class="text-xs text-gray-500">March 29, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$24.75</div>
</div>
</div>
</section>
<!-- Spending Limits -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Spending Limits</h2>
<button class="bg-primary text-white text-xs px-3 py-1.5 !rounded-button flex items-center cursor-pointer" id="addLimitBtn">
<i class="ri-add-line ri-sm mr-1"></i>
<span>Add Limit</span>
</button>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mr-3">
<i class="ri-shopping-bag-line text-purple-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shopping</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-purple-500 rounded-full" style="width: 80%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$400 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-restaurant-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Restaurants</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-blue-500 rounded-full" style="width: 65%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$300 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full mr-3">
<i class="ri-taxi-line text-green-500"></i>
</div>
<div>
<div class="text-sm font-medium">Transportation</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-green-500 rounded-full" style="width: 45%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$200 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
</div>
</section>
</main>
<!-- Tab Bar -->
<nav class="fixed bottom-0 w-full bg-white border-t border-gray-200 flex justify-between items-center px-2 py-2 z-50">
<a href="#" class="flex flex-col items-center justify-center w-1/5 text-primary cursor-pointer" id="homeTab">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-home-5-line ri-lg"></i>
</div>
<span class="text-xs mt-1">Home</span>
</a>
<a href="#" class="flex flex-col items-center justify-center w-1/5 text-gray-500 cursor-pointer" id="transactionsTab">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-exchange-line ri-lg"></i>
</div>
<span class="text-xs mt-1">Transactions</span>
</a>
<a href="#" class="flex flex-col items-center justify-center w-1/5 cursor-pointer" id="addTransactionBtn">
<div class="w-12 h-12 bg-primary rounded-full flex items-center justify-center -mt-5">
<i class="ri-add-line ri-xl text-white"></i>
</div>
</a>
<a href="#" class="flex flex-col items-center justify-center w-1/5 text-gray-500 cursor-pointer" id="budgetTab">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-pie-chart-line ri-lg"></i>
</div>
<span class="text-xs mt-1">Budget</span>
</a>
<a href="#" class="flex flex-col items-center justify-center w-1/5 text-gray-500 cursor-pointer" id="profileTab">
<div class="w-6 h-6 flex items-center justify-center">
<i class="ri-user-3-line ri-lg"></i>
</div>
<span class="text-xs mt-1">Profile</span>
</a>
</nav>
<script>
// Toggle switches
const toggles = document.querySelectorAll('input[type="checkbox"]');
toggles.forEach(toggle => {
toggle.addEventListener('change', function() {
const toggleSpan = this.nextElementSibling;
if (this.checked) {
toggleSpan.classList.add('bg-primary');
toggleSpan.classList.remove('bg-gray-300');
toggleSpan.querySelector('::before').style.transform = 'translateX(20px)';
} else {
toggleSpan.classList.remove('bg-primary');
toggleSpan.classList.add('bg-gray-300');
toggleSpan.querySelector('::before').style.transform = 'translateX(0)';
}
});
});
// Transaction filter buttons
const filterButtons = document.querySelectorAll('#filterAll, #filterIncome, #filterExpense');
filterButtons.forEach(button => {
button.addEventListener('click', function() {
filterButtons.forEach(btn => {
btn.classList.remove('bg-primary', 'text-white');
btn.classList.add('bg-gray-100', 'text-gray-500');
});
this.classList.remove('bg-gray-100', 'text-gray-500');
this.classList.add('bg-primary', 'text-white');
// Filter transactions based on button clicked
const transactions = document.querySelectorAll('.transaction-item');
if (this.id === 'filterAll') {
transactions.forEach(item => item.style.display = 'flex');
} else if (this.id === 'filterIncome') {
transactions.forEach(item => {
if (item.classList.contains('income-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
} else if (this.id === 'filterExpense') {
transactions.forEach(item => {
if (item.classList.contains('expense-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
}
});
});
// Splash screen handling
document.addEventListener('DOMContentLoaded', function() {
// Initialize financial data if not exists
initializeFinancialData();
const splashScreen = document.querySelector('.splash-screen');
// Check if this is the first load or a return to home
const isFirstLoad = sessionStorage.getItem('appLoaded') !== 'true';
if (isFirstLoad) {
// First time loading the app - show splash screen
sessionStorage.setItem('appLoaded', 'true');
// Hide splash screen after animation completes
setTimeout(() => {
if (splashScreen) {
splashScreen.style.display = 'none';
}
}, 3500); // 3.5 seconds total (2s delay + 1.5s animation)
} else {
// Returning to home - hide splash screen immediately
if (splashScreen) {
splashScreen.style.display = 'none';
}
}
// Make sure splash screen doesn't show when navigating back to home
window.addEventListener('popstate', function() {
if (splashScreen) {
splashScreen.style.display = 'none';
}
});
// Function to show notifications
window.showNotification = function(message) {
const notification = document.createElement('div');
notification.className = 'fixed top-20 left-1/2 transform -translate-x-1/2 bg-primary text-white px-4 py-2 rounded shadow-lg z-50 flex items-center';
notification.innerHTML = `
<i class="ri-checkbox-circle-line ri-lg mr-2"></i>
<span>${message}</span>
`;
document.body.appendChild(notification);
setTimeout(() => {
notification.classList.add('opacity-0', 'transition-opacity', 'duration-300');
setTimeout(() => notification.remove(), 300);
}, 2000);
};
// Initialize financial data
function initializeFinancialData() {
if (!localStorage.getItem('financialData')) {
const initialData = {
balance: 4285.65,
income: {
total: 6240.00,
transactions: [
{ id: 1, amount: 3250.00, category: 'salary', date: '2025-04-01', note: 'Monthly salary' },
{ id: 2, amount: 125.50, category: 'investment', date: '2025-03-30', note: 'Stock dividend' },
{ id: 3, amount: 750.00, category: 'other', date: '2025-03-25', note: 'Tax refund' },
{ id: 4, amount: 2114.50, category: 'freelance', date: '2025-03-15', note: 'Freelance project' }
]
},
expenses: {
total: 1954.35,
transactions: [
{ id: 1, amount: 85.32, category: 'food', date: '2025-04-03', note: 'Whole Foods Market' },
{ id: 2, amount: 15.99, category: 'entertainment', date: '2025-03-31', note: 'Netflix Subscription' },
{ id: 3, amount: 32.48, category: 'food', date: '2025-03-30', note: 'Shake Shack' },
{ id: 4, amount: 24.75, category: 'transportation', date: '2025-03-29', note: 'Uber Ride' },
{ id: 5, amount: 67.99, category: 'shopping', date: '2025-03-22', note: 'Amazon Purchase' },
{ id: 6, amount: 1727.82, category: 'other', date: '2025-03-10', note: 'Various expenses' }
]
},
savings: 2135.65,
budgets: {
food: { limit: 600, spent: 450 },
transportation: { limit: 300, spent: 180 },
shopping: { limit: 400, spent: 320 },
entertainment: { limit: 200, spent: 120 },
utilities: { limit: 300, spent: 180 }
},
goals: [
{ id: 1, name: 'Save for Vacation', target: 3000, current: 1500, date: '2025-08-15', priority: 'medium' },
{ id: 2, name: 'Emergency Fund', target: 10000, current: 4500, date: '2025-12-31', priority: 'high' }
]
};
localStorage.setItem('financialData', JSON.stringify(initialData));
}
}
// Get financial data
function getFinancialData() {
return JSON.parse(localStorage.getItem('financialData'));
}
// Save financial data
function saveFinancialData(data) {
localStorage.setItem('financialData', JSON.stringify(data));
}
// Add income
function addIncome(amount, category, date, note) {
const data = getFinancialData();
const newId = data.income.transactions.length > 0 ? 
    Math.max(...data.income.transactions.map(t => t.id)) + 1 : 1;
    
const newTransaction = {
    id: newId,
    amount: amount,
    category: category,
    date: date,
    note: note
};
data.income.transactions.unshift(newTransaction);
data.income.total += amount;
data.balance += amount;
saveFinancialData(data);
// Add to recent transactions list
addTransactionToUI(newTransaction, 'income');
}
// Add expense
function addExpense(amount, category, date, note) {
const data = getFinancialData();
const newId = data.expenses.transactions.length > 0 ? 
    Math.max(...data.expenses.transactions.map(t => t.id)) + 1 : 1;
    
const newTransaction = {
    id: newId,
    amount: amount,
    category: category,
    date: date,
    note: note
};
data.expenses.transactions.unshift(newTransaction);
data.expenses.total += amount;
data.balance -= amount;
// Update budget if category exists
if (data.budgets[category]) {
    data.budgets[category].spent += amount;
}
saveFinancialData(data);
// Add to recent transactions list
addTransactionToUI(newTransaction, 'expense');
}
// Add transaction to UI
function addTransactionToUI(transaction, type) {
const transactionsList = document.querySelector('.bg-white.rounded-lg.shadow-sm.overflow-hidden');
if (!transactionsList) return;
const iconClass = type === 'income' ? 
    'ri-bank-card-line text-blue-500' : 
    getCategoryIcon(transaction.category);
    
const bgClass = type === 'income' ? 'bg-blue-100' : 'bg-red-100';
const amountClass = type === 'income' ? 'text-green-500' : 'text-red-500';
const amountPrefix = type === 'income' ? '+' : '-';
const formattedDate = new Date(transaction.date).toLocaleDateString('en-US', {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
});
const newTransactionHTML = `
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item ${type}-transaction">
    <div class="flex items-center">
        <div class="w-8 h-8 flex items-center justify-center ${bgClass} rounded-full mr-3">
            <i class="${iconClass}"></i>
        </div>
        <div>
            <div class="text-sm font-medium">${transaction.note || getCategoryName(transaction.category)}</div>
            <div class="text-xs text-gray-500">${formattedDate}</div>
        </div>
    </div>
    <div class="text-sm font-medium ${amountClass}">${amountPrefix}$${transaction.amount.toFixed(2)}</div>
</div>
`;
// Insert at the top of the list
const firstTransaction = transactionsList.querySelector('.transaction-item');
if (firstTransaction) {
    firstTransaction.insertAdjacentHTML('beforebegin', newTransactionHTML);
} else {
    transactionsList.innerHTML = newTransactionHTML;
}
// If there are more than 6 transactions, remove the last one
const allTransactions = transactionsList.querySelectorAll('.transaction-item');
if (allTransactions.length > 6) {
    allTransactions[allTransactions.length - 1].remove();
}
}
// Get category icon
function getCategoryIcon(category) {
switch(category) {
    case 'food': return 'ri-restaurant-line text-red-500';
    case 'transportation': return 'ri-taxi-line text-red-500';
    case 'shopping': return 'ri-shopping-bag-line text-red-500';
    case 'entertainment': return 'ri-movie-line text-red-500';
    case 'utilities': return 'ri-home-line text-red-500';
    case 'salary': return 'ri-bank-card-line text-blue-500';
    case 'freelance': return 'ri-briefcase-line text-blue-500';
    case 'investment': return 'ri-funds-line text-blue-500';
    case 'gift': return 'ri-gift-line text-blue-500';
    default: return 'ri-question-line text-gray-500';
}
}
// Get category name
function getCategoryName(category) {
switch(category) {
    case 'food': return 'Food & Dining';
    case 'transportation': return 'Transportation';
    case 'shopping': return 'Shopping';
    case 'entertainment': return 'Entertainment';
    case 'utilities': return 'Utilities';
    case 'salary': return 'Salary';
    case 'freelance': return 'Freelance Income';
    case 'investment': return 'Investment Return';
    case 'gift': return 'Gift Received';
    default: return 'Other';
}
}
// Update balance summary
function updateBalanceSummary() {
const data = getFinancialData();
const balanceElement = document.querySelector('h3.text-2xl.font-bold');
const incomeElement = document.querySelector('.bg-white.p-3.rounded.shadow-sm:nth-child(1) .font-semibold.text-sm');
const expensesElement = document.querySelector('.bg-white.p-3.rounded.shadow-sm:nth-child(2) .font-semibold.text-sm');
const savingsElement = document.querySelector('.bg-white.p-3.rounded.shadow-sm:nth-child(3) .font-semibold.text-sm');
if (balanceElement) balanceElement.textContent = `$${data.balance.toFixed(2)}`;
if (incomeElement) incomeElement.textContent = `$${data.income.total.toFixed(2)}`;
if (expensesElement) expensesElement.textContent = `$${data.expenses.total.toFixed(2)}`;
if (savingsElement) savingsElement.textContent = `$${data.savings.toFixed(2)}`;
// Update budget progress
updateBudgetProgress();
}
// Update budget progress
function updateBudgetProgress() {
const data = getFinancialData();
const budgetElements = document.querySelectorAll('.progress-ring');
if (budgetElements.length >= 3) {
    // Food & Dining
    const foodPercentage = Math.min(100, Math.round((data.budgets.food.spent / data.budgets.food.limit) * 100));
    const foodOffset = 175.9 - (175.9 * foodPercentage / 100);
    budgetElements[0].querySelector('circle:nth-child(2)').setAttribute('stroke-dashoffset', foodOffset);
    budgetElements[0].parentElement.querySelector('.absolute.inset-0 div').textContent = `${foodPercentage}%`;
    budgetElements[0].parentElement.parentElement.querySelector('.text-xs.text-gray-500.mt-1').textContent = 
        `$${data.budgets.food.spent} / $${data.budgets.food.limit}`;
    
    // Transportation
    const transportPercentage = Math.min(100, Math.round((data.budgets.transportation.spent / data.budgets.transportation.limit) * 100));
    const transportOffset = 175.9 - (175.9 * transportPercentage / 100);
    budgetElements[1].querySelector('circle:nth-child(2)').setAttribute('stroke-dashoffset', transportOffset);
    budgetElements[1].parentElement.querySelector('.absolute.inset-0 div').textContent = `${transportPercentage}%`;
    budgetElements[1].parentElement.parentElement.querySelector('.text-xs.text-gray-500.mt-1').textContent = 
        `$${data.budgets.transportation.spent} / $${data.budgets.transportation.limit}`;
    
    // Shopping
    const shoppingPercentage = Math.min(100, Math.round((data.budgets.shopping.spent / data.budgets.shopping.limit) * 100));
    const shoppingOffset = 175.9 - (175.9 * shoppingPercentage / 100);
    budgetElements[2].querySelector('circle:nth-child(2)').setAttribute('stroke-dashoffset', shoppingOffset);
    budgetElements[2].parentElement.querySelector('.absolute.inset-0 div').textContent = `${shoppingPercentage}%`;
    budgetElements[2].parentElement.parentElement.querySelector('.text-xs.text-gray-500.mt-1').textContent = 
        `$${data.budgets.shopping.spent} / $${data.budgets.shopping.limit}`;
}
}
// Login modal
const profileBtn = document.getElementById('profileBtn');
if (profileBtn) {
profileBtn.addEventListener('click', showLoginModal);
}
// Add Income button
const addIncomeBtn = document.getElementById('addIncomeBtn');
if (addIncomeBtn) {
addIncomeBtn.addEventListener('click', showAddIncomeModal);
}
// Add Expense button
const addExpenseBtn = document.getElementById('addExpenseBtn');
if (addExpenseBtn) {
addExpenseBtn.addEventListener('click', showAddExpenseModal);
}
// View All Budget button
const viewAllBudgetBtn = document.getElementById('viewAllBudgetBtn');
if (viewAllBudgetBtn) {
viewAllBudgetBtn.addEventListener('click', function(e) {
e.preventDefault();
showBudgetDetailsModal();
});
}
// Add Limit button
const addLimitBtn = document.getElementById('addLimitBtn');
if (addLimitBtn) {
addLimitBtn.addEventListener('click', showAddLimitModal);
}
// Tab navigation
const homeTab = document.getElementById('homeTab');
const transactionsTab = document.getElementById('transactionsTab');
const addTransactionBtn = document.getElementById('addTransactionBtn');
const budgetTab = document.getElementById('budgetTab');
const profileTab = document.getElementById('profileTab');
if (homeTab) homeTab.addEventListener('click', function(e) {
e.preventDefault();
activateTab(homeTab);
// Reset the main content to the home page without reloading
const mainContent = document.querySelector('main');
// Get the original HTML content from the document
const originalMainContent = `
<!-- Balance Summary -->
<section class="mb-6 mt-4">
<div class="flex justify-between items-center mb-2">
<h2 class="text-sm text-gray-500">Total Balance</h2>
<div class="text-xs text-gray-500 bg-gray-100 px-2 py-1 rounded-full">April 2025</div>
</div>
<div class="flex justify-between items-end mb-2">
<h3 class="text-2xl font-bold">$4,285.65</h3>
<div class="flex items-center text-xs text-green-500">
<i class="ri-arrow-up-line ri-sm mr-1"></i>
<span>+2.5% from last month</span>
</div>
</div>
<div class="flex gap-2 mt-4">
<button class="flex-1 bg-primary text-white py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addIncomeBtn">
<i class="ri-add-line ri-lg mr-1"></i>
<span>Add Income</span>
</button>
<button class="flex-1 bg-white border border-gray-200 text-gray-700 py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addExpenseBtn">
<i class="ri-subtract-line ri-lg mr-1"></i>
<span>Add Expense</span>
</button>
</div>
</section>
<!-- Financial Overview -->
<section class="mb-6">
<div class="grid grid-cols-3 gap-3">
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mb-2">
<i class="ri-wallet-3-line text-blue-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Income</div>
<div class="font-semibold text-sm">$6,240.00</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mb-2">
<i class="ri-shopping-bag-line text-red-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Expenses</div>
<div class="font-semibold text-sm">$1,954.35</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mb-2">
<i class="ri-bank-line text-purple-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Savings</div>
<div class="font-semibold text-sm">$2,135.65</div>
</div>
</div>
</section>
<!-- Budget Progress -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Budget Progress</h2>
<a href="#" class="text-xs text-primary flex items-center cursor-pointer" id="viewAllBudgetBtn">
View All
<i class="ri-arrow-right-s-line ri-sm ml-1"></i>
</a>
</div>
<div class="grid grid-cols-3 gap-3">
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#6366f1" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="44"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">75%</div>
</div>
<div class="text-xs text-center">Food & Dining</div>
<div class="text-xs text-gray-500 mt-1">$450 / $600</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="70.4"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">60%</div>
</div>
<div class="text-xs text-center">Transportation</div>
<div class="text-xs text-gray-500 mt-1">$180 / $300</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="35.2"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">80%</div>
</div>
<div class="text-xs text-center">Shopping</div>
<div class="text-xs text-gray-500 mt-1">$320 / $400</div>
</div>
</div>
</section>
<!-- Recent Transactions -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Recent Transactions</h2>
<div class="flex gap-2">
<button class="text-xs bg-primary text-white px-2 py-1 rounded-full cursor-pointer" id="filterAll">All</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterIncome">Income</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterExpense">Expense</button>
</div>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-bank-card-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Salary Deposit</div>
<div class="text-xs text-gray-500">April 1, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$3,250.00</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-shopping-basket-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Whole Foods Market</div>
<div class="text-xs text-gray-500">April 3, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$85.32</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-netflex-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Netflix Subscription</div>
<div class="text-xs text-gray-500">March 31, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$15.99</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-funds-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Stock Dividend</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$125.50</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-restaurant-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shake Shack</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$32.48</div>
</div>
<div class="p-3 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-taxi-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Uber Ride</div>
<div class="text-xs text-gray-500">March 29, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$24.75</div>
</div>
</div>
</section>
<!-- Spending Limits -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Spending Limits</h2>
<button class="bg-primary text-white text-xs px-3 py-1.5 !rounded-button flex items-center cursor-pointer" id="addLimitBtn">
<i class="ri-add-line ri-sm mr-1"></i>
<span>Add Limit</span>
</button>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mr-3">
<i class="ri-shopping-bag-line text-purple-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shopping</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-purple-500 rounded-full" style="width: 80%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$400 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-restaurant-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Restaurants</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-blue-500 rounded-full" style="width: 65%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$300 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full mr-3">
<i class="ri-taxi-line text-green-500"></i>
</div>
<div>
<div class="text-sm font-medium">Transportation</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-green-500 rounded-full" style="width: 45%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$200 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
</div>
</section>
`;
mainContent.innerHTML = originalMainContent;
// Reattach event listeners for the home page
attachHomePageEventListeners();
});
if (transactionsTab) transactionsTab.addEventListener('click', function(e) {
e.preventDefault();
activateTab(transactionsTab);
showTransactionsPage();
});
if (addTransactionBtn) addTransactionBtn.addEventListener('click', function(e) {
e.preventDefault();
showAddTransactionModal();
});
if (budgetTab) budgetTab.addEventListener('click', function(e) {
e.preventDefault();
activateTab(budgetTab);
showBudgetPage();
});
if (profileTab) profileTab.addEventListener('click', function(e) {
e.preventDefault();
activateTab(profileTab);
showProfilePage();
});
});
// Function to activate tab
function activateTab(activeTab) {
const allTabs = [homeTab, transactionsTab, budgetTab, profileTab];
allTabs.forEach(tab => {
if (tab) {
tab.classList.remove('text-primary');
tab.classList.add('text-gray-500');
}
});
if (activeTab) {
activeTab.classList.remove('text-gray-500');
activeTab.classList.add('text-primary');
}
}
// Modal functions
function createModal(title, content, onSubmit) {
// Remove any existing modals
const existingModal = document.querySelector('.modal-container');
if (existingModal) {
existingModal.remove();
}
const modalContainer = document.createElement('div');
modalContainer.className = 'modal-container fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-[100]';
const modalContent = document.createElement('div');
modalContent.className = 'bg-white rounded-lg w-[90%] max-w-md overflow-hidden';
const modalHeader = document.createElement('div');
modalHeader.className = 'bg-primary text-white px-4 py-3 flex justify-between items-center';
modalHeader.innerHTML = `
<h3 class="font-medium">${title}</h3>
<button class="modal-close-btn">
<i class="ri-close-line ri-lg"></i>
</button>
`;
const modalBody = document.createElement('div');
modalBody.className = 'p-4';
modalBody.innerHTML = content;
const modalFooter = document.createElement('div');
modalFooter.className = 'px-4 py-3 bg-gray-50 flex justify-end gap-2';
modalFooter.innerHTML = `
<button class="modal-cancel-btn px-4 py-2 bg-gray-200 text-gray-700 !rounded-button">Cancel</button>
<button class="modal-submit-btn px-4 py-2 bg-primary text-white !rounded-button">Submit</button>
`;
modalContent.appendChild(modalHeader);
modalContent.appendChild(modalBody);
modalContent.appendChild(modalFooter);
modalContainer.appendChild(modalContent);
document.body.appendChild(modalContainer);
// Add event listeners
const closeBtn = modalContainer.querySelector('.modal-close-btn');
const cancelBtn = modalContainer.querySelector('.modal-cancel-btn');
const submitBtn = modalContainer.querySelector('.modal-submit-btn');
closeBtn.addEventListener('click', () => modalContainer.remove());
cancelBtn.addEventListener('click', () => modalContainer.remove());
submitBtn.addEventListener('click', () => {
if (onSubmit) {
onSubmit(modalContainer);
}
modalContainer.remove();
});
return modalContainer;
}
function showLoginModal() {
const content = `
<div class="flex justify-center gap-4 mb-4">
<button id="loginTabBtn" class="px-4 py-2 bg-primary text-white !rounded-button">Login</button>
<button id="signupTabBtn" class="px-4 py-2 bg-gray-200 text-gray-700 !rounded-button">Sign Up</button>
</div>
<form id="loginForm">
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
<input type="email" class="w-full px-3 py-2 border border-gray-300 rounded" placeholder="Enter your email" required>
</div>
<div class="mb-2">
<label class="block text-sm font-medium text-gray-700 mb-1">Password</label>
<input type="password" class="w-full px-3 py-2 border border-gray-300 rounded" placeholder="Enter your password" required>
</div>
<div class="mb-4 text-right">
<a href="#" class="text-xs text-primary">Forgot password?</a>
</div>
</form>
<form id="signupForm" class="hidden">
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
<input type="text" class="w-full px-3 py-2 border border-gray-300 rounded" placeholder="Enter your full name" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
<input type="email" class="w-full px-3 py-2 border border-gray-300 rounded" placeholder="Enter your email" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Password</label>
<input type="password" class="w-full px-3 py-2 border border-gray-300 rounded" placeholder="Create a password" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Confirm Password</label>
<input type="password" class="w-full px-3 py-2 border border-gray-300 rounded" placeholder="Confirm your password" required>
</div>
</form>
`;
const modal = createModal('Account', content, (modal) => {
const activeForm = modal.querySelector('#loginForm').classList.contains('hidden') ?
modal.querySelector('#signupForm') :
modal.querySelector('#loginForm');
// Handle login/signup logic here
console.log(activeForm.id === 'loginForm' ? 'Login submitted' : 'Signup submitted');
// Show success notification
showNotification(activeForm.id === 'loginForm' ? 'Login successful!' : 'Account created successfully!');
});
const submitBtn = modal.querySelector('.modal-submit-btn');
submitBtn.textContent = 'Login';
// Tab switching logic
const loginTabBtn = modal.querySelector('#loginTabBtn');
const signupTabBtn = modal.querySelector('#signupTabBtn');
const loginForm = modal.querySelector('#loginForm');
const signupForm = modal.querySelector('#signupForm');
loginTabBtn.addEventListener('click', () => {
loginTabBtn.classList.add('bg-primary', 'text-white');
loginTabBtn.classList.remove('bg-gray-200', 'text-gray-700');
signupTabBtn.classList.add('bg-gray-200', 'text-gray-700');
signupTabBtn.classList.remove('bg-primary', 'text-white');
loginForm.classList.remove('hidden');
signupForm.classList.add('hidden');
submitBtn.textContent = 'Login';
});
signupTabBtn.addEventListener('click', () => {
signupTabBtn.classList.add('bg-primary', 'text-white');
signupTabBtn.classList.remove('bg-gray-200', 'text-gray-700');
loginTabBtn.classList.add('bg-gray-200', 'text-gray-700');
loginTabBtn.classList.remove('bg-primary', 'text-white');
signupForm.classList.remove('hidden');
loginForm.classList.add('hidden');
submitBtn.textContent = 'Sign Up';
});
}
function showAddIncomeModal() {
const content = `
<form id="addIncomeForm">
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Amount</label>
<div class="relative">
<span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
<input type="number" id="incomeAmount" class="w-full pl-8 pr-3 py-2 border border-gray-300 rounded" placeholder="0.00" step="0.01" min="0" required>
</div>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Category</label>
<select id="incomeCategory" class="w-full px-3 py-2 border border-gray-300 rounded bg-white">
<option value="salary">Salary</option>
<option value="freelance">Freelance</option>
<option value="investment">Investment</option>
<option value="gift">Gift</option>
<option value="other">Other</option>
</select>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Date</label>
<input type="date" id="incomeDate" class="w-full px-3 py-2 border border-gray-300 rounded" value="${new Date().toISOString().split('T')[0]}" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Note</label>
<textarea id="incomeNote" class="w-full px-3 py-2 border border-gray-300 rounded" rows="2" placeholder="Add a note (optional)"></textarea>
</div>
</form>
`;
const modal = createModal('Add Income', content, (modal) => {
const form = modal.querySelector('#addIncomeForm');
const amount = modal.querySelector('#incomeAmount').value;
const category = modal.querySelector('#incomeCategory').value;
const date = modal.querySelector('#incomeDate').value;
const note = modal.querySelector('#incomeNote').value;
if (!amount || isNaN(parseFloat(amount)) || parseFloat(amount) <= 0) {
showNotification('Please enter a valid amount');
return;
}
// Add income to storage
addIncome(parseFloat(amount), category, date, note);
showNotification('Income added successfully!');
updateBalanceSummary();
});
const submitBtn = modal.querySelector('.modal-submit-btn');
submitBtn.textContent = 'Add Income';
}
function showAddExpenseModal() {
const content = `
<form id="addExpenseForm">
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Amount</label>
<div class="relative">
<span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
<input type="number" id="expenseAmount" class="w-full pl-8 pr-3 py-2 border border-gray-300 rounded" placeholder="0.00" step="0.01" min="0" required>
</div>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Category</label>
<select id="expenseCategory" class="w-full px-3 py-2 border border-gray-300 rounded bg-white">
<option value="food">Food & Dining</option>
<option value="transportation">Transportation</option>
<option value="shopping">Shopping</option>
<option value="entertainment">Entertainment</option>
<option value="utilities">Utilities</option>
<option value="other">Other</option>
</select>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Date</label>
<input type="date" id="expenseDate" class="w-full px-3 py-2 border border-gray-300 rounded" value="${new Date().toISOString().split('T')[0]}" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Note</label>
<textarea id="expenseNote" class="w-full px-3 py-2 border border-gray-300 rounded" rows="2" placeholder="Add a note (optional)"></textarea>
</div>
</form>
`;
const modal = createModal('Add Expense', content, (modal) => {
const form = modal.querySelector('#addExpenseForm');
const amount = modal.querySelector('#expenseAmount').value;
const category = modal.querySelector('#expenseCategory').value;
const date = modal.querySelector('#expenseDate').value;
const note = modal.querySelector('#expenseNote').value;
if (!amount || isNaN(parseFloat(amount)) || parseFloat(amount) <= 0) {
showNotification('Please enter a valid amount');
return;
}
// Add expense to storage
addExpense(parseFloat(amount), category, date, note);
showNotification('Expense added successfully!');
updateBalanceSummary();
});
const submitBtn = modal.querySelector('.modal-submit-btn');
submitBtn.textContent = 'Add Expense';
}
function showBudgetDetailsModal() {
const content = `
<div class="mb-4">
<h4 class="font-medium mb-2">Monthly Budget Overview</h4>
<div class="bg-gray-100 p-3 rounded mb-3">
<div class="flex justify-between mb-1">
<span class="text-sm">Total Budget</span>
<span class="text-sm font-medium">$2,500.00</span>
</div>
<div class="flex justify-between mb-1">
<span class="text-sm">Spent</span>
<span class="text-sm font-medium">$1,250.35</span>
</div>
<div class="flex justify-between">
<span class="text-sm">Remaining</span>
<span class="text-sm font-medium text-green-500">$1,249.65</span>
</div>
</div>
</div>
<div>
<h4 class="font-medium mb-2">Category Breakdown</h4>
<div class="space-y-3">
<div class="flex justify-between items-center">
<div>
<div class="flex items-center">
<div class="w-3 h-3 bg-blue-500 rounded-full mr-2"></div>
<span class="text-sm">Food & Dining</span>
</div>
<div class="text-xs text-gray-500">$450 / $600</div>
</div>
<div class="text-sm font-medium">75%</div>
</div>
<div class="flex justify-between items-center">
<div>
<div class="flex items-center">
<div class="w-3 h-3 bg-orange-500 rounded-full mr-2"></div>
<span class="text-sm">Transportation</span>
</div>
<div class="text-xs text-gray-500">$180 / $300</div>
</div>
<div class="text-sm font-medium">60%</div>
</div>
<div class="flex justify-between items-center">
<div>
<div class="flex items-center">
<div class="w-3 h-3 bg-purple-500 rounded-full mr-2"></div>
<span class="text-sm">Shopping</span>
</div>
<div class="text-xs text-gray-500">$320 / $400</div>
</div>
<div class="text-sm font-medium">80%</div>
</div>
<div class="flex justify-between items-center">
<div>
<div class="flex items-center">
<div class="w-3 h-3 bg-green-500 rounded-full mr-2"></div>
<span class="text-sm">Entertainment</span>
</div>
<div class="text-xs text-gray-500">$120 / $200</div>
</div>
<div class="text-sm font-medium">60%</div>
</div>
<div class="flex justify-between items-center">
<div>
<div class="flex items-center">
<div class="w-3 h-3 bg-red-500 rounded-full mr-2"></div>
<span class="text-sm">Utilities</span>
</div>
<div class="text-xs text-gray-500">$180 / $300</div>
</div>
<div class="text-sm font-medium">60%</div>
</div>
</div>
</div>
`;
const modal = createModal('Budget Details', content);
const submitBtn = modal.querySelector('.modal-submit-btn');
submitBtn.textContent = 'Close';
const cancelBtn = modal.querySelector('.modal-cancel-btn');
cancelBtn.style.display = 'none';
}
function showAddLimitModal() {
const content = `
<form id="addLimitForm">
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Category</label>
<select class="w-full px-3 py-2 border border-gray-300 rounded bg-white">
<option value="">Select a category</option>
<option value="entertainment">Entertainment</option>
<option value="utilities">Utilities</option>
<option value="groceries">Groceries</option>
<option value="clothing">Clothing</option>
<option value="health">Health & Wellness</option>
</select>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Limit Amount</label>
<div class="relative">
<span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
<input type="number" class="w-full pl-8 pr-3 py-2 border border-gray-300 rounded" placeholder="0.00" step="0.01" min="0" required>
</div>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Period</label>
<select class="w-full px-3 py-2 border border-gray-300 rounded bg-white">
<option value="weekly">Weekly</option>
<option value="monthly" selected>Monthly</option>
<option value="yearly">Yearly</option>
</select>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Notification</label>
<div class="flex items-center">
<label class="relative inline-block w-10 h-5 cursor-pointer mr-2">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
<span class="text-sm">Notify me when I reach 80% of the limit</span>
</div>
</div>
</form>
`;
const modal = createModal('Add Spending Limit', content, (modal) => {
const form = modal.querySelector('#addLimitForm');
// Handle add limit logic here
console.log('Limit added');
});
const submitBtn = modal.querySelector('.modal-submit-btn');
submitBtn.textContent = 'Add Limit';
}
function showAddTransactionModal() {
const content = `
<div class="flex justify-center gap-4 mb-4">
<button id="incomeTabBtn" class="px-4 py-2 bg-primary text-white !rounded-button">Income</button>
<button id="expenseTabBtn" class="px-4 py-2 bg-gray-200 text-gray-700 !rounded-button">Expense</button>
</div>
<form id="addTransactionForm">
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Amount</label>
<div class="relative">
<span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
<input type="number" id="transactionAmount" class="w-full pl-8 pr-3 py-2 border border-gray-300 rounded" placeholder="0.00" step="0.01" min="0" required>
</div>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Category</label>
<select class="w-full px-3 py-2 border border-gray-300 rounded bg-white" id="categorySelect">
<option value="salary">Salary</option>
<option value="freelance">Freelance</option>
<option value="investment">Investment</option>
<option value="gift">Gift</option>
<option value="other">Other</option>
</select>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Date</label>
<input type="date" id="transactionDate" class="w-full px-3 py-2 border border-gray-300 rounded" value="${new Date().toISOString().split('T')[0]}" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Note</label>
<textarea id="transactionNote" class="w-full px-3 py-2 border border-gray-300 rounded" rows="2" placeholder="Add a note (optional)"></textarea>
</div>
</form>
`;
const modal = createModal('Add Transaction', content, (modal) => {
const form = modal.querySelector('#addTransactionForm');
const isIncome = modal.querySelector('#incomeTabBtn').classList.contains('bg-primary');
const amount = modal.querySelector('#transactionAmount').value;
const category = modal.querySelector('#categorySelect').value;
const date = modal.querySelector('#transactionDate').value;
const note = modal.querySelector('#transactionNote').value;
if (!amount || isNaN(parseFloat(amount)) || parseFloat(amount) <= 0) {
showNotification('Please enter a valid amount');
return;
}
if (isIncome) {
addIncome(parseFloat(amount), category, date, note);
} else {
addExpense(parseFloat(amount), category, date, note);
}
// Show success notification
showNotification(`${isIncome ? 'Income' : 'Expense'} added successfully!`);
updateBalanceSummary();
});
const submitBtn = modal.querySelector('.modal-submit-btn');
submitBtn.textContent = 'Add Transaction';
// Tab switching logic
const incomeTabBtn = modal.querySelector('#incomeTabBtn');
const expenseTabBtn = modal.querySelector('#expenseTabBtn');
const categorySelect = modal.querySelector('#categorySelect');
incomeTabBtn.addEventListener('click', () => {
incomeTabBtn.classList.add('bg-primary', 'text-white');
incomeTabBtn.classList.remove('bg-gray-200', 'text-gray-700');
expenseTabBtn.classList.add('bg-gray-200', 'text-gray-700');
expenseTabBtn.classList.remove('bg-primary', 'text-white');
// Update categories for income
categorySelect.innerHTML = `
<option value="salary">Salary</option>
<option value="freelance">Freelance</option>
<option value="investment">Investment</option>
<option value="gift">Gift</option>
<option value="other">Other</option>
`;
});
expenseTabBtn.addEventListener('click', () => {
expenseTabBtn.classList.add('bg-primary', 'text-white');
expenseTabBtn.classList.remove('bg-gray-200', 'text-gray-700');
incomeTabBtn.classList.add('bg-gray-200', 'text-gray-700');
incomeTabBtn.classList.remove('bg-primary', 'text-white');
// Update categories for expense
categorySelect.innerHTML = `
<option value="food">Food & Dining</option>
<option value="transportation">Transportation</option>
<option value="shopping">Shopping</option>
<option value="entertainment">Entertainment</option>
<option value="utilities">Utilities</option>
<option value="other">Other</option>
`;
});
}
// Page navigation functions
function showTransactionsPage() {
// Hide main content and show transactions page
const mainContent = document.querySelector('main');
mainContent.innerHTML = `
<div class="pt-16 pb-16 px-4">
<section class="mb-6 mt-4">
<div class="flex items-center mb-4">
<a href="#" class="mr-2" id="backToHomeBtn">
<i class="ri-arrow-left-line ri-lg text-gray-500"></i>
</a>
<h2 class="text-xl font-medium">Transaction History</h2>
</div>
<div class="flex justify-between items-center mb-4">
<div class="flex gap-2">
<button class="text-xs bg-primary text-white px-2 py-1 rounded-full cursor-pointer" id="historyFilterAll">All</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="historyFilterIncome">Income</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="historyFilterExpense">Expense</button>
</div>
<div class="text-xs text-gray-500 bg-gray-100 px-2 py-1 rounded-full">April 2025</div>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden mb-4">
<div class="p-3 border-b border-gray-100 flex justify-between items-center history-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-bank-card-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Salary Deposit</div>
<div class="text-xs text-gray-500">April 1, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$3,250.00</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center history-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-shopping-basket-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Whole Foods Market</div>
<div class="text-xs text-gray-500">April 3, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$85.32</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center history-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-netflex-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Netflix Subscription</div>
<div class="text-xs text-gray-500">March 31, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$15.99</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center history-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-funds-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Stock Dividend</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$125.50</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center history-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-restaurant-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shake Shack</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$32.48</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center history-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-taxi-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Uber Ride</div>
<div class="text-xs text-gray-500">March 29, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$24.75</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center history-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-refund-2-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Tax Refund</div>
<div class="text-xs text-gray-500">March 25, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$750.00</div>
</div>
<div class="p-3 flex justify-between items-center history-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-shopping-bag-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Amazon Purchase</div>
<div class="text-xs text-gray-500">March 22, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$67.99</div>
</div>
</div>
<div class="flex justify-center">
<button class="text-primary text-sm flex items-center">
Load More
<i class="ri-arrow-down-s-line ri-sm ml-1"></i>
</button>
</div>
</section>
</div>
`;
// Add event listeners for the filter buttons
const historyFilterButtons = document.querySelectorAll('#historyFilterAll, #historyFilterIncome, #historyFilterExpense');
historyFilterButtons.forEach(button => {
button.addEventListener('click', function() {
historyFilterButtons.forEach(btn => {
btn.classList.remove('bg-primary', 'text-white');
btn.classList.add('bg-gray-100', 'text-gray-500');
});
this.classList.remove('bg-gray-100', 'text-gray-500');
this.classList.add('bg-primary', 'text-white');
// Filter transactions based on button clicked
const historyItems = document.querySelectorAll('.history-item');
if (this.id === 'historyFilterAll') {
historyItems.forEach(item => item.style.display = 'flex');
} else if (this.id === 'historyFilterIncome') {
historyItems.forEach(item => {
if (item.classList.contains('income-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
} else if (this.id === 'historyFilterExpense') {
historyItems.forEach(item => {
if (item.classList.contains('expense-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
}
});
});
// Add event listener for back button
const backToHomeBtn = document.getElementById('backToHomeBtn');
if (backToHomeBtn) {
backToHomeBtn.addEventListener('click', function(e) {
e.preventDefault();
// Reset the main content to the home page without reloading
const mainContent = document.querySelector('main');
// Get the original HTML content directly
const originalMainContent = `
<!-- Balance Summary -->
<section class="mb-6 mt-4">
<div class="flex justify-between items-center mb-2">
<h2 class="text-sm text-gray-500">Total Balance</h2>
<div class="text-xs text-gray-500 bg-gray-100 px-2 py-1 rounded-full">April 2025</div>
</div>
<div class="flex justify-between items-end mb-2">
<h3 class="text-2xl font-bold">$4,285.65</h3>
<div class="flex items-center text-xs text-green-500">
<i class="ri-arrow-up-line ri-sm mr-1"></i>
<span>+2.5% from last month</span>
</div>
</div>
<div class="flex gap-2 mt-4">
<button class="flex-1 bg-primary text-white py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addIncomeBtn">
<i class="ri-add-line ri-lg mr-1"></i>
<span>Add Income</span>
</button>
<button class="flex-1 bg-white border border-gray-200 text-gray-700 py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addExpenseBtn">
<i class="ri-subtract-line ri-lg mr-1"></i>
<span>Add Expense</span>
</button>
</div>
</section>
<!-- Financial Overview -->
<section class="mb-6">
<div class="grid grid-cols-3 gap-3">
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mb-2">
<i class="ri-wallet-3-line text-blue-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Income</div>
<div class="font-semibold text-sm">$6,240.00</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mb-2">
<i class="ri-shopping-bag-line text-red-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Expenses</div>
<div class="font-semibold text-sm">$1,954.35</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mb-2">
<i class="ri-bank-line text-purple-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Savings</div>
<div class="font-semibold text-sm">$2,135.65</div>
</div>
</div>
</section>
<!-- Budget Progress -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Budget Progress</h2>
<a href="#" class="text-xs text-primary flex items-center cursor-pointer" id="viewAllBudgetBtn">
View All
<i class="ri-arrow-right-s-line ri-sm ml-1"></i>
</a>
</div>
<div class="grid grid-cols-3 gap-3">
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#6366f1" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="44"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">75%</div>
</div>
<div class="text-xs text-center">Food & Dining</div>
<div class="text-xs text-gray-500 mt-1">$450 / $600</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="70.4"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">60%</div>
</div>
<div class="text-xs text-center">Transportation</div>
<div class="text-xs text-gray-500 mt-1">$180 / $300</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="35.2"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">80%</div>
</div>
<div class="text-xs text-center">Shopping</div>
<div class="text-xs text-gray-500 mt-1">$320 / $400</div>
</div>
</div>
</section>
<!-- Recent Transactions -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Recent Transactions</h2>
<div class="flex gap-2">
<button class="text-xs bg-primary text-white px-2 py-1 rounded-full cursor-pointer" id="filterAll">All</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterIncome">Income</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterExpense">Expense</button>
</div>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-bank-card-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Salary Deposit</div>
<div class="text-xs text-gray-500">April 1, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$3,250.00</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-shopping-basket-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Whole Foods Market</div>
<div class="text-xs text-gray-500">April 3, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$85.32</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-netflex-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Netflix Subscription</div>
<div class="text-xs text-gray-500">March 31, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$15.99</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-funds-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Stock Dividend</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$125.50</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-restaurant-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shake Shack</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$32.48</div>
</div>
<div class="p-3 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-taxi-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Uber Ride</div>
<div class="text-xs text-gray-500">March 29, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$24.75</div>
</div>
</div>
</section>
<!-- Spending Limits -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Spending Limits</h2>
<button class="bg-primary text-white text-xs px-3 py-1.5 !rounded-button flex items-center cursor-pointer" id="addLimitBtn">
<i class="ri-add-line ri-sm mr-1"></i>
<span>Add Limit</span>
</button>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mr-3">
<i class="ri-shopping-bag-line text-purple-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shopping</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-purple-500 rounded-full" style="width: 80%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$400 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-restaurant-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Restaurants</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-blue-500 rounded-full" style="width: 65%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$300 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full mr-3">
<i class="ri-taxi-line text-green-500"></i>
</div>
<div>
<div class="text-sm font-medium">Transportation</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-green-500 rounded-full" style="width: 45%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$200 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
</div>
</section>
`;
mainContent.innerHTML = originalMainContent;
activateTab(homeTab);
// Reattach event listeners for the home page
attachHomePageEventListeners();
// Make sure splash screen is hidden
const splashScreen = document.querySelector('.splash-screen');
if (splashScreen) {
splashScreen.style.display = 'none';
}
});
}
// Function to attach event listeners for home page elements
function attachHomePageEventListeners() {
const addIncomeBtn = document.getElementById('addIncomeBtn');
if (addIncomeBtn) {
addIncomeBtn.addEventListener('click', showAddIncomeModal);
}
const addExpenseBtn = document.getElementById('addExpenseBtn');
if (addExpenseBtn) {
addExpenseBtn.addEventListener('click', showAddExpenseModal);
}
const viewAllBudgetBtn = document.getElementById('viewAllBudgetBtn');
if (viewAllBudgetBtn) {
viewAllBudgetBtn.addEventListener('click', function(e) {
e.preventDefault();
showBudgetDetailsModal();
});
}
const addLimitBtn = document.getElementById('addLimitBtn');
if (addLimitBtn) {
addLimitBtn.addEventListener('click', showAddLimitModal);
}
const filterButtons = document.querySelectorAll('#filterAll, #filterIncome, #filterExpense');
filterButtons.forEach(button => {
button.addEventListener('click', function() {
filterButtons.forEach(btn => {
btn.classList.remove('bg-primary', 'text-white');
btn.classList.add('bg-gray-100', 'text-gray-500');
});
this.classList.remove('bg-gray-100', 'text-gray-500');
this.classList.add('bg-primary', 'text-white');
// Filter transactions based on button clicked
const transactions = document.querySelectorAll('.transaction-item');
if (this.id === 'filterAll') {
transactions.forEach(item => item.style.display = 'flex');
} else if (this.id === 'filterIncome') {
transactions.forEach(item => {
if (item.classList.contains('income-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
} else if (this.id === 'filterExpense') {
transactions.forEach(item => {
if (item.classList.contains('expense-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
}
});
});
}
// Show notification
showNotification('Transactions Page Loaded');
}
function showBudgetPage() {
// Hide main content and show budget page
const mainContent = document.querySelector('main');
mainContent.innerHTML = `
<div class="pt-16 pb-16 px-4">
<section class="mb-6 mt-4">
<div class="flex items-center mb-4">
<a href="#" class="mr-2" id="backToHomeBtn">
<i class="ri-arrow-left-line ri-lg text-gray-500"></i>
</a>
<h2 class="text-xl font-medium">Budget Overview</h2>
<div class="text-xs text-gray-500 bg-gray-100 px-2 py-1 rounded-full ml-auto">April 2025</div>
</div>
<div class="bg-white rounded-lg shadow-sm p-4 mb-6">
<div class="flex justify-between mb-2">
<span class="text-sm text-gray-500">Total Budget</span>
<span class="text-sm font-medium">$2,500.00</span>
</div>
<div class="flex justify-between mb-2">
<span class="text-sm text-gray-500">Spent</span>
<span class="text-sm font-medium">$1,250.35</span>
</div>
<div class="flex justify-between mb-4">
<span class="text-sm text-gray-500">Remaining</span>
<span class="text-sm font-medium text-green-500">$1,249.65</span>
</div>
<div class="w-full h-2 bg-gray-200 rounded-full">
<div class="h-full bg-primary rounded-full" style="width: 50%"></div>
</div>
<div class="text-xs text-gray-500 text-right mt-1">50% spent</div>
</div>
<h3 class="font-medium mb-3">Category Breakdown</h3>
<div class="bg-white rounded-lg shadow-sm overflow-hidden mb-6">
<div class="p-4 border-b border-gray-100">
<div class="flex justify-between items-center mb-2">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-restaurant-line text-blue-500"></i>
</div>
<span class="text-sm font-medium">Food & Dining</span>
</div>
<span class="text-sm font-medium">75%</span>
</div>
<div class="text-xs text-gray-500 mb-2">$450 / $600</div>
<div class="w-full h-1.5 bg-gray-200 rounded-full">
<div class="h-full bg-blue-500 rounded-full" style="width: 75%"></div>
</div>
</div>
<div class="p-4 border-b border-gray-100">
<div class="flex justify-between items-center mb-2">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-orange-100 rounded-full mr-3">
<i class="ri-taxi-line text-orange-500"></i>
</div>
<span class="text-sm font-medium">Transportation</span>
</div>
<span class="text-sm font-medium">60%</span>
</div>
<div class="text-xs text-gray-500 mb-2">$180 / $300</div>
<div class="w-full h-1.5 bg-gray-200 rounded-full">
<div class="h-full bg-orange-500 rounded-full" style="width: 60%"></div>
</div>
</div>
<div class="p-4 border-b border-gray-100">
<div class="flex justify-between items-center mb-2">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mr-3">
<i class="ri-shopping-bag-line text-purple-500"></i>
</div>
<span class="text-sm font-medium">Shopping</span>
</div>
<span class="text-sm font-medium">80%</span>
</div>
<div class="text-xs text-gray-500 mb-2">$320 / $400</div>
<div class="w-full h-1.5 bg-gray-200 rounded-full">
<div class="h-full bg-purple-500 rounded-full" style="width: 80%"></div>
</div>
</div>
<div class="p-4 border-b border-gray-100">
<div class="flex justify-between items-center mb-2">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full mr-3">
<i class="ri-movie-line text-green-500"></i>
</div>
<span class="text-sm font-medium">Entertainment</span>
</div>
<span class="text-sm font-medium">60%</span>
</div>
<div class="text-xs text-gray-500 mb-2">$120 / $200</div>
<div class="w-full h-1.5 bg-gray-200 rounded-full">
<div class="h-full bg-green-500 rounded-full" style="width: 60%"></div>
</div>
</div>
<div class="p-4">
<div class="flex justify-between items-center mb-2">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-home-line text-red-500"></i>
</div>
<span class="text-sm font-medium">Utilities</span>
</div>
<span class="text-sm font-medium">60%</span>
</div>
<div class="text-xs text-gray-500 mb-2">$180 / $300</div>
<div class="w-full h-1.5 bg-gray-200 rounded-full">
<div class="h-full bg-red-500 rounded-full" style="width: 60%"></div>
</div>
</div>
</div>
<div class="flex justify-between items-center mb-4">
<h3 class="font-medium">Budget Goals</h3>
<button class="bg-primary text-white text-xs px-3 py-1.5 !rounded-button flex items-center cursor-pointer" id="addGoalBtn">
<i class="ri-add-line ri-sm mr-1"></i>
<span>Add Goal</span>
</button>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-4 border-b border-gray-100">
<div class="flex justify-between items-center mb-2">
<span class="text-sm font-medium">Save for Vacation</span>
<span class="text-xs bg-blue-100 text-blue-600 px-2 py-0.5 rounded-full">In Progress</span>
</div>
<div class="text-xs text-gray-500 mb-2">$1,500 / $3,000 (50%)</div>
<div class="w-full h-1.5 bg-gray-200 rounded-full">
<div class="h-full bg-blue-500 rounded-full" style="width: 50%"></div>
</div>
<div class="text-xs text-gray-500 mt-2">Target date: August 15, 2025</div>
</div>
<div class="p-4">
<div class="flex justify-between items-center mb-2">
<span class="text-sm font-medium">Emergency Fund</span>
<span class="text-xs bg-green-100 text-green-600 px-2 py-0.5 rounded-full">On Track</span>
</div>
<div class="text-xs text-gray-500 mb-2">$4,500 / $10,000 (45%)</div>
<div class="w-full h-1.5 bg-gray-200 rounded-full">
<div class="h-full bg-green-500 rounded-full" style="width: 45%"></div>
</div>
<div class="text-xs text-gray-500 mt-2">Target date: December 31, 2025</div>
</div>
</div>
</section>
</div>
`;
// Add event listener for the add goal button
const addGoalBtn = document.getElementById('addGoalBtn');
if (addGoalBtn) {
addGoalBtn.addEventListener('click', showAddGoalModal);
}
// Add event listener for back button
const backToHomeBtn = document.getElementById('backToHomeBtn');
if (backToHomeBtn) {
backToHomeBtn.addEventListener('click', function(e) {
e.preventDefault();
// Reset the main content to the home page without reloading
const mainContent = document.querySelector('main');
// Get the original HTML content directly
const originalMainContent = `
<!-- Balance Summary -->
<section class="mb-6 mt-4">
<div class="flex justify-between items-center mb-2">
<h2 class="text-sm text-gray-500">Total Balance</h2>
<div class="text-xs text-gray-500 bg-gray-100 px-2 py-1 rounded-full">April 2025</div>
</div>
<div class="flex justify-between items-end mb-2">
<h3 class="text-2xl font-bold">$4,285.65</h3>
<div class="flex items-center text-xs text-green-500">
<i class="ri-arrow-up-line ri-sm mr-1"></i>
<span>+2.5% from last month</span>
</div>
</div>
<div class="flex gap-2 mt-4">
<button class="flex-1 bg-primary text-white py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addIncomeBtn">
<i class="ri-add-line ri-lg mr-1"></i>
<span>Add Income</span>
</button>
<button class="flex-1 bg-white border border-gray-200 text-gray-700 py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addExpenseBtn">
<i class="ri-subtract-line ri-lg mr-1"></i>
<span>Add Expense</span>
</button>
</div>
</section>
<!-- Financial Overview -->
<section class="mb-6">
<div class="grid grid-cols-3 gap-3">
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mb-2">
<i class="ri-wallet-3-line text-blue-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Income</div>
<div class="font-semibold text-sm">$6,240.00</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mb-2">
<i class="ri-shopping-bag-line text-red-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Expenses</div>
<div class="font-semibold text-sm">$1,954.35</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mb-2">
<i class="ri-bank-line text-purple-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Savings</div>
<div class="font-semibold text-sm">$2,135.65</div>
</div>
</div>
</section>
<!-- Budget Progress -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Budget Progress</h2>
<a href="#" class="text-xs text-primary flex items-center cursor-pointer" id="viewAllBudgetBtn">
View All
<i class="ri-arrow-right-s-line ri-sm ml-1"></i>
</a>
</div>
<div class="grid grid-cols-3 gap-3">
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#6366f1" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="44"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">75%</div>
</div>
<div class="text-xs text-center">Food & Dining</div>
<div class="text-xs text-gray-500 mt-1">$450 / $600</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="70.4"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">60%</div>
</div>
<div class="text-xs text-center">Transportation</div>
<div class="text-xs text-gray-500 mt-1">$180 / $300</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="35.2"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">80%</div>
</div>
<div class="text-xs text-center">Shopping</div>
<div class="text-xs text-gray-500 mt-1">$320 / $400</div>
</div>
</div>
</section>
<!-- Recent Transactions -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Recent Transactions</h2>
<div class="flex gap-2">
<button class="text-xs bg-primary text-white px-2 py-1 rounded-full cursor-pointer" id="filterAll">All</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterIncome">Income</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterExpense">Expense</button>
</div>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-bank-card-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Salary Deposit</div>
<div class="text-xs text-gray-500">April 1, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$3,250.00</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-shopping-basket-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Whole Foods Market</div>
<div class="text-xs text-gray-500">April 3, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$85.32</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-netflex-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Netflix Subscription</div>
<div class="text-xs text-gray-500">March 31, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$15.99</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-funds-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Stock Dividend</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$125.50</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-restaurant-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shake Shack</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$32.48</div>
</div>
<div class="p-3 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-taxi-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Uber Ride</div>
<div class="text-xs text-gray-500">March 29, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$24.75</div>
</div>
</div>
</section>
<!-- Spending Limits -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Spending Limits</h2>
<button class="bg-primary text-white text-xs px-3 py-1.5 !rounded-button flex items-center cursor-pointer" id="addLimitBtn">
<i class="ri-add-line ri-sm mr-1"></i>
<span>Add Limit</span>
</button>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mr-3">
<i class="ri-shopping-bag-line text-purple-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shopping</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-purple-500 rounded-full" style="width: 80%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$400 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-restaurant-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Restaurants</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-blue-500 rounded-full" style="width: 65%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$300 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full mr-3">
<i class="ri-taxi-line text-green-500"></i>
</div>
<div>
<div class="text-sm font-medium">Transportation</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-green-500 rounded-full" style="width: 45%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$200 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
</div>
</section>
`;
mainContent.innerHTML = originalMainContent;
activateTab(homeTab);
// Reattach event listeners for the home page
attachHomePageEventListeners();
// Make sure splash screen is hidden
const splashScreen = document.querySelector('.splash-screen');
if (splashScreen) {
splashScreen.style.display = 'none';
}
});
}
// Function to attach event listeners for home page elements
function attachHomePageEventListeners() {
const addIncomeBtn = document.getElementById('addIncomeBtn');
if (addIncomeBtn) {
addIncomeBtn.addEventListener('click', showAddIncomeModal);
}
const addExpenseBtn = document.getElementById('addExpenseBtn');
if (addExpenseBtn) {
addExpenseBtn.addEventListener('click', showAddExpenseModal);
}
const viewAllBudgetBtn = document.getElementById('viewAllBudgetBtn');
if (viewAllBudgetBtn) {
viewAllBudgetBtn.addEventListener('click', function(e) {
e.preventDefault();
showBudgetDetailsModal();
});
}
const addLimitBtn = document.getElementById('addLimitBtn');
if (addLimitBtn) {
addLimitBtn.addEventListener('click', showAddLimitModal);
}
const filterButtons = document.querySelectorAll('#filterAll, #filterIncome, #filterExpense');
filterButtons.forEach(button => {
button.addEventListener('click', function() {
filterButtons.forEach(btn => {
btn.classList.remove('bg-primary', 'text-white');
btn.classList.add('bg-gray-100', 'text-gray-500');
});
this.classList.remove('bg-gray-100', 'text-gray-500');
this.classList.add('bg-primary', 'text-white');
// Filter transactions based on button clicked
const transactions = document.querySelectorAll('.transaction-item');
if (this.id === 'filterAll') {
transactions.forEach(item => item.style.display = 'flex');
} else if (this.id === 'filterIncome') {
transactions.forEach(item => {
if (item.classList.contains('income-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
} else if (this.id === 'filterExpense') {
transactions.forEach(item => {
if (item.classList.contains('expense-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
}
});
});
}
// Show notification
showNotification('Budget Page Loaded');
}
function showAddGoalModal() {
const content = `
<form id="addGoalForm">
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Goal Name</label>
<input type="text" class="w-full px-3 py-2 border border-gray-300 rounded" placeholder="e.g. New Laptop, Vacation" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Target Amount</label>
<div class="relative">
<span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
<input type="number" class="w-full pl-8 pr-3 py-2 border border-gray-300 rounded" placeholder="0.00" step="0.01" min="0" required>
</div>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Current Savings</label>
<div class="relative">
<span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
<input type="number" class="w-full pl-8 pr-3 py-2 border border-gray-300 rounded" placeholder="0.00" step="0.01" min="0" required>
</div>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Target Date</label>
<input type="date" class="w-full px-3 py-2 border border-gray-300 rounded" required>
</div>
<div class="mb-4">
<label class="block text-sm font-medium text-gray-700 mb-1">Priority</label>
<select class="w-full px-3 py-2 border border-gray-300 rounded bg-white">
<option value="high">High</option>
<option value="medium" selected>Medium</option>
<option value="low">Low</option>
</select>
</div>
</form>
`;
const modal = createModal('Add Budget Goal', content, (modal) => {
const form = modal.querySelector('#addGoalForm');
// Handle add goal logic here
console.log('Goal added');
showNotification('Budget goal added successfully!');
});
const submitBtn = modal.querySelector('.modal-submit-btn');
submitBtn.textContent = 'Add Goal';
}
function showProfilePage() {
// Hide main content and show profile page
const mainContent = document.querySelector('main');
mainContent.innerHTML = `
<div class="pt-16 pb-16 px-4">
<section class="mb-6 mt-4">
<div class="flex items-center mb-6">
<a href="#" class="mr-2" id="backToHomeBtn">
<i class="ri-arrow-left-line ri-lg text-gray-500"></i>
</a>
<h2 class="text-xl font-medium">Profile</h2>
</div>
<!-- Profile Header -->
<div class="bg-white rounded-lg shadow-sm p-4 mb-4">
<div class="flex items-center">
<div class="w-16 h-16 rounded-full overflow-hidden mr-4">
<img src="https://readdy.ai/api/search-image?query=cartoon avatar of a young woman, minimalist design, flat illustration style, simple features, professional look, light background, clean design, the icon should take up 70 of the frame, centered composition&width=100&height=100&seq=123&orientation=squarish" alt="Profile" class="w-full h-full object-cover">
</div>
<div>
<h3 class="text-lg font-medium">Alex Morgan</h3>
<p class="text-sm text-gray-500">alex.morgan@example.com</p>
<div class="flex items-center mt-1">
<span class="text-xs bg-green-100 text-green-600 px-2 py-0.5 rounded-full">Premium Member</span>
</div>
</div>
</div>
</div>
<!-- Account Stats -->
<div class="grid grid-cols-3 gap-3 mb-4">
<div class="bg-white p-3 rounded shadow-sm text-center">
<p class="text-xs text-gray-500 mb-1">Balance</p>
<p class="font-semibold">$4,285.65</p>
</div>
<div class="bg-white p-3 rounded shadow-sm text-center">
<p class="text-xs text-gray-500 mb-1">Savings</p>
<p class="font-semibold">$2,135.65</p>
</div>
<div class="bg-white p-3 rounded shadow-sm text-center">
<p class="text-xs text-gray-500 mb-1">Goals</p>
<p class="font-semibold">2 Active</p>
</div>
</div>
<!-- Menu Items -->
<div class="bg-white rounded-lg shadow-sm overflow-hidden mb-4">
<a href="#" class="p-4 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-user-settings-line text-blue-500"></i>
</div>
<span class="text-sm">Account Settings</span>
</div>
<i class="ri-arrow-right-s-line text-gray-400"></i>
</a>
<a href="#" class="p-4 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mr-3">
<i class="ri-bank-card-line text-purple-500"></i>
</div>
<span class="text-sm">Payment Methods</span>
</div>
<i class="ri-arrow-right-s-line text-gray-400"></i>
</a>
<a href="#" class="p-4 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full mr-3">
<i class="ri-shield-check-line text-green-500"></i>
</div>
<span class="text-sm">Security</span>
</div>
<i class="ri-arrow-right-s-line text-gray-400"></i>
</a>
<a href="#" class="p-4 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-yellow-100 rounded-full mr-3">
<i class="ri-notification-3-line text-yellow-500"></i>
</div>
<span class="text-sm">Notifications</span>
</div>
<i class="ri-arrow-right-s-line text-gray-400"></i>
</a>
<a href="#" class="p-4 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-question-line text-red-500"></i>
</div>
<span class="text-sm">Help & Support</span>
</div>
<i class="ri-arrow-right-s-line text-gray-400"></i>
</a>
</div>
<!-- Subscription -->
<div class="bg-white rounded-lg shadow-sm p-4 mb-4">
<div class="flex justify-between items-center mb-3">
<h3 class="text-sm font-medium text-gray-700">Premium Subscription</h3>
<span class="text-xs bg-green-100 text-green-600 px-2 py-0.5 rounded-full">Active</span>
</div>
<div class="text-xs text-gray-500 mb-3">Your premium plan renews on May 1, 2025</div>
<div class="flex justify-between items-center">
<button class="text-xs bg-primary text-white px-3 py-1.5 !rounded-button">Manage Subscription</button>
<button class="text-xs text-gray-500">View Benefits</button>
</div>
</div>
<!-- Sign Out Button -->
<button class="w-full bg-gray-100 text-gray-700 py-3 !rounded-button flex items-center justify-center cursor-pointer mb-4">
<i class="ri-logout-box-line ri-sm mr-2"></i>
<span>Sign Out</span>
</button>
<!-- App Info -->
<div class="text-center text-xs text-gray-500">
<p>FinTrack v2.5.1</p>
<p class="mt-1">© 2025 FinTrack Inc. All rights reserved.</p>
</div>
</section>
</div>
`;
// Add event listener for back button
const backToHomeBtn = document.getElementById('backToHomeBtn');
if (backToHomeBtn) {
backToHomeBtn.addEventListener('click', function(e) {
e.preventDefault();
// Reset the main content to the home page without reloading
const mainContent = document.querySelector('main');
// Get the original HTML content directly
const originalMainContent = `
<!-- Balance Summary -->
<section class="mb-6 mt-4">
<div class="flex justify-between items-center mb-2">
<h2 class="text-sm text-gray-500">Total Balance</h2>
<div class="text-xs text-gray-500 bg-gray-100 px-2 py-1 rounded-full">April 2025</div>
</div>
<div class="flex justify-between items-end mb-2">
<h3 class="text-2xl font-bold">$4,285.65</h3>
<div class="flex items-center text-xs text-green-500">
<i class="ri-arrow-up-line ri-sm mr-1"></i>
<span>+2.5% from last month</span>
</div>
</div>
<div class="flex gap-2 mt-4">
<button class="flex-1 bg-primary text-white py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addIncomeBtn">
<i class="ri-add-line ri-lg mr-1"></i>
<span>Add Income</span>
</button>
<button class="flex-1 bg-white border border-gray-200 text-gray-700 py-2.5 !rounded-button flex items-center justify-center cursor-pointer" id="addExpenseBtn">
<i class="ri-subtract-line ri-lg mr-1"></i>
<span>Add Expense</span>
</button>
</div>
</section>
<!-- Financial Overview -->
<section class="mb-6">
<div class="grid grid-cols-3 gap-3">
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mb-2">
<i class="ri-wallet-3-line text-blue-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Income</div>
<div class="font-semibold text-sm">$6,240.00</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mb-2">
<i class="ri-shopping-bag-line text-red-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Expenses</div>
<div class="font-semibold text-sm">$1,954.35</div>
</div>
<div class="bg-white p-3 rounded shadow-sm">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mb-2">
<i class="ri-bank-line text-purple-500"></i>
</div>
<div class="text-xs text-gray-500 mb-1">Savings</div>
<div class="font-semibold text-sm">$2,135.65</div>
</div>
</div>
</section>
<!-- Budget Progress -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Budget Progress</h2>
<a href="#" class="text-xs text-primary flex items-center cursor-pointer" id="viewAllBudgetBtn">
View All
<i class="ri-arrow-right-s-line ri-sm ml-1"></i>
</a>
</div>
<div class="grid grid-cols-3 gap-3">
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#6366f1" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="44"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">75%</div>
</div>
<div class="text-xs text-center">Food & Dining</div>
<div class="text-xs text-gray-500 mt-1">$450 / $600</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="70.4"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">60%</div>
</div>
<div class="text-xs text-center">Transportation</div>
<div class="text-xs text-gray-500 mt-1">$180 / $300</div>
</div>
<div class="flex flex-col items-center">
<div class="relative w-16 h-16 mb-2">
<svg class="progress-ring" width="64" height="64">
<circle class="progress-ring__circle" stroke="#e0e0e0" stroke-width="4" fill="transparent" r="28" cx="32" cy="32"/>
<circle class="progress-ring__circle" stroke="#f97316" stroke-width="4" fill="transparent" r="28" cx="32" cy="32" stroke-dasharray="175.9" stroke-dashoffset="35.2"/>
</svg>
<div class="absolute inset-0 flex items-center justify-center text-xs font-medium">80%</div>
</div>
<div class="text-xs text-center">Shopping</div>
<div class="text-xs text-gray-500 mt-1">$320 / $400</div>
</div>
</div>
</section>
<!-- Recent Transactions -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Recent Transactions</h2>
<div class="flex gap-2">
<button class="text-xs bg-primary text-white px-2 py-1 rounded-full cursor-pointer" id="filterAll">All</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterIncome">Income</button>
<button class="text-xs bg-gray-100 text-gray-500 px-2 py-1 rounded-full cursor-pointer" id="filterExpense">Expense</button>
</div>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-bank-card-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Salary Deposit</div>
<div class="text-xs text-gray-500">April 1, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$3,250.00</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-shopping-basket-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Whole Foods Market</div>
<div class="text-xs text-gray-500">April 3, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$85.32</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-netflex-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Netflix Subscription</div>
<div class="text-xs text-gray-500">March 31, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$15.99</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item income-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-funds-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Stock Dividend</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-green-500">+$125.50</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-restaurant-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shake Shack</div>
<div class="text-xs text-gray-500">March 30, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$32.48</div>
</div>
<div class="p-3 flex justify-between items-center transaction-item expense-transaction">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-red-100 rounded-full mr-3">
<i class="ri-taxi-line text-red-500"></i>
</div>
<div>
<div class="text-sm font-medium">Uber Ride</div>
<div class="text-xs text-gray-500">March 29, 2025</div>
</div>
</div>
<div class="text-sm font-medium text-red-500">-$24.75</div>
</div>
</div>
</section>
<!-- Spending Limits -->
<section class="mb-6">
<div class="flex justify-between items-center mb-4">
<h2 class="font-medium">Spending Limits</h2>
<button class="bg-primary text-white text-xs px-3 py-1.5 !rounded-button flex items-center cursor-pointer" id="addLimitBtn">
<i class="ri-add-line ri-sm mr-1"></i>
<span>Add Limit</span>
</button>
</div>
<div class="bg-white rounded-lg shadow-sm overflow-hidden">
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-purple-100 rounded-full mr-3">
<i class="ri-shopping-bag-line text-purple-500"></i>
</div>
<div>
<div class="text-sm font-medium">Shopping</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-purple-500 rounded-full" style="width: 80%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$400 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 border-b border-gray-100 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-blue-100 rounded-full mr-3">
<i class="ri-restaurant-line text-blue-500"></i>
</div>
<div>
<div class="text-sm font-medium">Restaurants</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-blue-500 rounded-full" style="width: 65%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$300 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
<div class="p-3 flex justify-between items-center">
<div class="flex items-center">
<div class="w-8 h-8 flex items-center justify-center bg-green-100 rounded-full mr-3">
<i class="ri-taxi-line text-green-500"></i>
</div>
<div>
<div class="text-sm font-medium">Transportation</div>
<div class="w-24 h-1.5 bg-gray-200 rounded-full mt-1">
<div class="h-full bg-green-500 rounded-full" style="width: 45%"></div>
</div>
</div>
</div>
<div class="flex items-center gap-3">
<div class="text-right">
<div class="text-xs text-gray-500">Limit</div>
<div class="text-sm font-medium">$200 / month</div>
</div>
<label class="relative inline-block w-10 h-5 cursor-pointer">
<input type="checkbox" class="opacity-0 w-0 h-0" checked>
<span class="absolute inset-0 rounded-full bg-primary transition-all before:content-[''] before:absolute before:h-4 before:w-4 before:left-0.5 before:bottom-0.5 before:bg-white before:rounded-full before:transition-all before:translate-x-5"></span>
</label>
</div>
</div>
</div>
</section>
`;
mainContent.innerHTML = originalMainContent;
activateTab(homeTab);
// Reattach event listeners for the home page
attachHomePageEventListeners();
// Make sure splash screen is hidden
const splashScreen = document.querySelector('.splash-screen');
if (splashScreen) {
splashScreen.style.display = 'none';
}
});
}
// Function to attach event listeners for home page elements
function attachHomePageEventListeners() {
const addIncomeBtn = document.getElementById('addIncomeBtn');
if (addIncomeBtn) {
addIncomeBtn.addEventListener('click', showAddIncomeModal);
}
const addExpenseBtn = document.getElementById('addExpenseBtn');
if (addExpenseBtn) {
addExpenseBtn.addEventListener('click', showAddExpenseModal);
}
const viewAllBudgetBtn = document.getElementById('viewAllBudgetBtn');
if (viewAllBudgetBtn) {
viewAllBudgetBtn.addEventListener('click', function(e) {
e.preventDefault();
showBudgetDetailsModal();
});
}
const addLimitBtn = document.getElementById('addLimitBtn');
if (addLimitBtn) {
addLimitBtn.addEventListener('click', showAddLimitModal);
}
const filterButtons = document.querySelectorAll('#filterAll, #filterIncome, #filterExpense');
filterButtons.forEach(button => {
button.addEventListener('click', function() {
filterButtons.forEach(btn => {
btn.classList.remove('bg-primary', 'text-white');
btn.classList.add('bg-gray-100', 'text-gray-500');
});
this.classList.remove('bg-gray-100', 'text-gray-500');
this.classList.add('bg-primary', 'text-white');
// Filter transactions based on button clicked
const transactions = document.querySelectorAll('.transaction-item');
if (this.id === 'filterAll') {
transactions.forEach(item => item.style.display = 'flex');
} else if (this.id === 'filterIncome') {
transactions.forEach(item => {
if (item.classList.contains('income-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
} else if (this.id === 'filterExpense') {
transactions.forEach(item => {
if (item.classList.contains('expense-transaction')) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
}
});
});
}
// Add event listeners for toggle switches
const toggles = document.querySelectorAll('input[type="checkbox"]');
toggles.forEach(toggle => {
toggle.addEventListener('change', function() {
const toggleSpan = this.nextElementSibling;
if (this.checked) {
toggleSpan.classList.add('bg-primary');
toggleSpan.classList.remove('bg-gray-300');
toggleSpan.querySelector('::before').style.transform = 'translateX(20px)';
} else {
toggleSpan.classList.remove('bg-primary');
toggleSpan.classList.add('bg-gray-300');
toggleSpan.querySelector('::before').style.transform = 'translateX(0)';
}
});
});
// Show notification
showNotification('Profile Page Loaded');
}
</script>
</body>
</html>
