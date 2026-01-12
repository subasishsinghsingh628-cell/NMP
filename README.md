<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Terms of Service - NMP (No more poor)</title>
    <style>body{font-family:Arial,sans-serif;margin:20px;max-width:800px;margin:auto;}h1{color:#007bff;}p{margin:10px 0;}</style>
</head>
<body>
    <h1>Terms of Service for NMP (No more poor)</h1>
    <p><strong>Last Updated:</strong> [Insert Date, e.g., October 2023]</p>
    <p>Welcome to NMP (No more poor). By using our app, you agree to these terms.</p>
    <ul>
        <li><strong>Eligibility:</strong> You must be at least 18 years old to use this service. If you are under 18, do not use this app.</li>
        <li><strong>Use:</strong> This app is for learning and earning opportunities. Misuse (e.g., illegal activities) is prohibited.</li>
        <li><strong>Earnings:</strong> We take a 30% commission on earnings. Payouts are subject to verification.</li>
        <li><strong>Liability:</strong> We are not responsible for third-party links or user actions.</li>
        <li><strong>Changes:</strong> We may update these terms at any time.</li>
    </ul>
    <p>Contact us at subasishsinghsingh628@gmail.com for questions.</p>
    <p><a href="index.html">Back to NMP</a></p>
</body>
</html>
{
    "name": "NMP (No more poor)",
    "short_name": "NMP",
    "description": "Free learning and earning opportunities for orphans, the poor, and those below the poverty line.",
    "start_url": "/",
    "display": "standalone",
    "background_color": "#f4f4f4",
    "theme_color": "#007bff",
    "icons": [
        {
            "src": "data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>NMP</text></svg>",
            "sizes": "192x192",
            "type": "image/svg+xml"
        },
        {
            "src": "data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>NMP</text></svg>",
            "sizes": "512x512",
            "type": "image/svg+xml"
        }
    ]
}
const CACHE_NAME = 'nmp-v1';
const urlsToCache = [
    '/',
    'index.html',
    'manifest.json',
    'terms.html',
    'privacy.html'
];

self.addEventListener('install', event => {
    event.waitUntil(
        caches.open(CACHE_NAME)
            .then(cache => cache.addAll(urlsToCache))
    );
});

self.addEventListener('fetch', event => {
    event.respondWith(
        caches.match(event.request)
            .then(response => response || fetch(event.request))
    );
});
