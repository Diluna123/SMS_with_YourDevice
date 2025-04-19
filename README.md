# SMS_with_YourDevice
# 📲 SMS8.io PHP API Wrapper

This is a PHP SDK to easily interact with the [SMS8.io](https://app.sms8.io) API for sending SMS/MMS, managing contacts, handling USSD requests, and retrieving device/message information.

---

## ⚙️ Installation

1. **Clone this repository or download the PHP file:**

```bash
git clone https://github.com/yourusername/sms8-php-api.git
Include the SDK in your PHP project:

require_once 'sms8.php'; // Adjust the path accordingly
```
## 🔑 Configuration
Open the file and replace the API key placeholder:

```define("API_KEY", "[YOUR-API]");```

Optionally, change the server URL if needed:

```define("SERVER", "https://app.sms8.io");```
## 🚀 Usage
1. Send a Single Message
```
$response = sendSingleMessage(
    "+11234567890",      // Number
    "Hello from SMS8!",  // Message
    1                    // Device ID (optional)
);
print_r($response);
```
3. Send Bulk Messages
```
$messages = [
    ['number' => '+11234567890', 'message' => 'Hello John!'],
    ['number' => '+11234567891', 'message' => 'Hello Jane!'],
];

$response = sendMessages($messages, USE_SPECIFIED, [1]);
print_r($response);
```
3. Send to a Contact List
```
$response = sendMessageToContactsList(101, 'Promo message to list');
print_r($response);
```
4. Add a Contact
```
$response = addContact(101, '+11234567890', 'John Doe');
print_r($response);
```
5. Check Balance
```
$balance = getBalance();
echo "Remaining Credits: $balance";
```

## 📚 Features
✅ Send SMS & MMS

📥 Receive and manage messages

📇 Manage contacts and contact lists

🔁 Resend failed messages

📱 USSD support

📊 Query message status, delivery, and history

🛠 Multiple device handling

## 🧪 Error Handling
All functions throw Exception if something goes wrong, so wrap your calls with try-catch blocks:

```
try {
    $response = sendSingleMessage("+11234567890", "Test message");
} catch (Exception $e) {
    echo "Error: " . $e->getMessage();
}
```
## 🖥️ Constants
```
USE_SPECIFIED     // Use specified devices
USE_ALL_DEVICES   // Use all devices and default SIMs
USE_ALL_SIMS      // Use all devices and all SIMs
```
## 📄 License
This project is open-source and free to use under the MIT License.

## ✉️ Contact
For questions or support, contact support@sms8.io or visit SMS8.io.
