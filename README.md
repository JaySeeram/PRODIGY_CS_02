# PRODIGY_CS_02
## Description
Pixel Manipulation for Image Encryption is a Python project that demonstrates a basic technique for image encryption and decryption using pixel channel swapping. Leveraging the power of the PIL (Python Imaging Library), this project shows how simple operations on pixel values can be used to obscure image content.

## Code
```
from PIL import Image

def encrypt_image(input_path, output_path, key):
    img = Image.open(input_path)
    pixels = img.load()

    width, height = img.size

    for i in range(width):
        for j in range(height):
            r, g, b = pixels[i, j]

            # swapping red and blue channels
            encrypted_pixel = (b, g, r)

            pixels[i, j] = encrypted_pixel

    img.save(output_path)
    print("Image encrypted successfully!")

def decrypt_image(input_path, output_path, key):
    img = Image.open(input_path)
    pixels = img.load()

    width, height = img.size

    for i in range(width):
        for j in range(height):
            r, g, b = pixels[i, j]

            # swapping red and blue channels back
            decrypted_pixel = (b, g, r)

            pixels[i, j] = decrypted_pixel

    img.save(output_path)
    print("Image decrypted successfully!")

 # image path
input_image = r"C:\Users\abu76\Desktop\Internship-01\Task-02\input.jpg"
encrypted_image = r"C:\Users\abu76\Desktop\Internship-01\Task-02\decrypted_image.jpg"
decrypted_image = r"C:\Users\abu76\Desktop\Internship-01\Task-02\encrypted_image.jpg"


# Encrypt the image
encrypt_image(input_image, encrypted_image, key=None)

# Decrypt the image
decrypt_image(encrypted_image, decrypted_image, key=None)
```
