# CurrencyFlow-PyQt5

A real-time currency converter desktop application built using PyQt5 and Python.

This project uses the Frankfurter Exchange Rate API to fetch live currency exchange rates and display converted values instantly through a simple graphical user interface.

---

## Features

- Real-time currency conversion
- PyQt5 graphical interface
- API integration using requests
- Multiple currency support
- Exception handling for network/API issues
- Simple and responsive UI

---

## Supported Currencies

```python
["USD","INR","EUR","GBP","JPY","CNY","CAD","AUD","CHF","SGD","HKD"]
```

---

## Technologies Used

- Python
- PyQt5
- Requests
- Frankfurter API

---

## How It Works

The application takes:

- Amount input from the user
- Source currency
- Target currency

After clicking the Convert button, the application sends a request to:

```python
url=f"https://api.frankfurter.app/latest?amount={amount}&from={from_currency}&to={to_currency}"
```

The API returns live exchange rate data which is then displayed inside the GUI.

---

## Main Conversion Logic

```python
response = requests.get(url)
response.raise_for_status()

data = response.json()
result = data['rates'][to_currency]

self.result_label.setText(f"{result}{to_currency}")
```

---

## Error Handling

The application handles multiple exceptions including:

```python
except ValueError:
except requests.exceptions.ConnectionError:
except requests.exceptions.Timeout:
except requests.exceptions.TooManyRedirects:
except requests.exceptions.RequestException:
except requests.exceptions.HTTPError:
```

This prevents crashes and provides proper error messages to the user.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/CurrencyFlow-PyQt5.git
```

Install dependencies:

```bash
pip install PyQt5 requests
```

Run the application:

```bash
python main.py
```

---

## Future Improvements

- Add dark mode
- Add currency swap button
- Add conversion history
- Improve UI styling
- Add more currencies dynamically
- Add loading animations

---

## API Used

https://www.frankfurter.app

---

## Author

Rajveer Singh Tanwar
