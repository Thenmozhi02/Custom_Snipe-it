Running the Project (WSL – Ubuntu)
Prerequisites:

WSL (Ubuntu)
PHP, MySQL
Node.js, NPM
Homebrew (Linuxbrew)
Snipe-IT project cloned locally

Step-by-Step Instructions
1. Open two WSL Ubuntu terminal windows (Windows PowerShell)

(Open both terminals with administrator privileges if required)

2. Navigate to the project directory (both terminals)
cd /mnt/d/snipe-it

3. Load Homebrew environment (both terminals)
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"

Terminal 1 – Application Setup

Run the following commands in order:

php artisan key:generate
php artisan migrate --seed
npm run dev
php artisan serve


The application will be available at:

http://127.0.0.1:8000

Terminal 2 – Database Operations
4. Load Homebrew environment
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"

5. Login to MySQL
mysql -u root -p

6. Update asset renewal date
UPDATE assets
SET renewal_date = '<yyyy-mm-dd>'
WHERE asset_tag = '<asset_tag>';


Example:

UPDATE assets
SET renewal_date = '2025-12-31'
WHERE asset_tag = 'LT-1023';
