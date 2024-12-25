# PyUtils3
- **PyUtils3** is a lightweight python package for utils
# Features
- **File Tools**: Write and read text or JSON files.
- **Network Tools**: Check internet connectivity for multiple sites.
- **Security Tools**: Generate strong passwords and encrypt/decrypt sensitive data.
- **Text Tools**: Analyze text and extract keywords.
- **Database Tools**: Save and load data to/from a file.
- **DDoS Tools**: Simulate a ddos attack (udp/botnet)
- **Web Tools**: Create a HTTP website from index.html file
# Package Guide
## #1 Installation
- you can install **PyUtils3** via pip:
```bash
pip install py-utils3
```
## #2 Usage
- here is a example usage about the package:
```python
from pyutils3 import *

def main():
    print("=== Example Usage of pyutils3 ===\n")

    # =============================
    # File Tools
    # =============================
    print(">>> File Tools <<<")
    write_file("example.txt", "Hello, world!")
    print("File 'example.txt' written.")

    content = read_file("example.txt")
    print(f"Content of 'example.txt': {content}")

    data = {"name": "Alice", "age": 25}
    write_file("data.json", data)
    print("File 'data.json' written.")

    json_content = read_file("data.json")
    print(f"Content of 'data.json': {json_content}\n")

    # =============================
    # Network Tools
    # =============================
    print(">>> Network Tools <<<")
    internet_status = check_internet()
    print(f"Internet status: {internet_status}\n")

    # =============================
    # Security Tools
    # =============================
    print(">>> Security Tools <<<")
    password = generate_password(16)
    print(f"Generated Password: {password} (Saved to 'password.txt')")

    data_to_encrypt = "Sensitive data"
    encrypted_data, encryption_key = encrypt_data(data_to_encrypt)
    print(f"Encrypted Data: {encrypted_data}")

    decrypted_data = decrypt_data(encrypted_data, encryption_key)
    print(f"Decrypted Data: {decrypted_data}\n")

    # =============================
    # Text Tools
    # =============================
    print(">>> Text Tools <<<")
    text = "Python is great. Python is simple."
    analysis = analyze_text(text)
    print("Text Analysis:")
    print(analysis)

    keywords = extract_keywords(text, top_n=2)
    print(f"Top Keywords: {keywords}\n")

    # =============================
    # Database Tools
    # =============================
    print(">>> Database Tools <<<")
    user_data = {"user1": {"name": "John", "age": 30}}
    save(user_data, "my_database.pkl")
    print("Data saved to 'my_database.pkl'.")

    loaded_data = load("my_database.pkl")
    print(f"Loaded Data: {loaded_data}\n")
    # =============================
    # web tools
    # =============================
    print(">>> web tools <<<")
    from pyutils3.web_tools import app

    host = "127.0.0.1"
    port = 8080

    @app.route("index.html")
    def page():
        return app.get_html_file()  # This will serve the     index.html file

# Run the app (default host="127.0.0.1" and port=8080)
    app.run()

    # ============================
    # ddos tools
    # ============================
    from pyutils3.ddos_tools import udp, botnet, layer_type

    # Define attack parameters
    target_ip = "192.168.0.1"
    target_port = 80
    layer = layer_type("layer7")  # Choose between "layer4" and "layer7"
    packets_count = 1000

    # Perform UDP flood attack
    udp(target_ip, target_port, layer, packets_count)

    # Perform Botnet attack
   botnet(target_ip, target_port, layer, packets_count)


    if __name = "__main__"
    main()
