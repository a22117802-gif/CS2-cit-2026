from cryptography.fernet import Fernet

# Générer une clé (ديرها غير مرة وحدة واحتافظ بها)
key = Fernet.generate_key()

# Sauvegarder la clé dans un fichier
with open("key.key", "wb") as key_file:
    key_file.write(key)

# Charger la clé
with open("key.key", "rb") as key_file:
    key = key_file.read()

fernet = Fernet(key)

# --------- CHIFFREMENT ---------
message = "Salam hadi risala sirriya"
message_bytes = message.encode()

encrypted = fernet.encrypt(message_bytes)
print("Message chiffré:", encrypted)

# --------- DECHIFFREMENT ---------
decrypted = fernet.decrypt(encrypted)
print("Message déchiffré:", decrypted.decode())
# CS2-cit-2026
