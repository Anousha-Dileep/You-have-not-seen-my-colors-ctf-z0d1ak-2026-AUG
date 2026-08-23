# **You Have Not Seen My Colors**

category: Cryptography

Author: TitanCode

# **Challenge Description:**

Elian gave you this challenge. Find meaning in the noise, then prove what you decoded to the private endpoint.

The answer is lowercase with words joined by underscores.

**No hint**

# **Files**
| File | Description |
|------|-------------|
| crypto_you-have-not-seen-my-colors (1).tar | the attached file was the main clue/ciphertext |
| an instance | Provided an instance-specific image and an endpoint where the decoded phrase could be submitted |

# **Analysis** 

The description indicates that the phrase will be in lower case.

After extracting the supplied archive, I found:

(text)
image.png

The image was a 100 × 100 RGB PNG and appeared to contain random colored noise.

At first glance, there was no readable text or obvious visual clue.

Because the challenge was called "You Have Not Seen My Colors", I suspected that the important information was not the visible image 

itself, but the underlying RGB color values.

An RGB pixel contains three values:

Pixel = (Red, Green, Blue)

Each channel is represented using 8 bits:

R = r7 r6 r5 r4 r3 r2 r1 r0

G = g7 g6 g5 g4 g3 g2 g1 g0

B = b7 b6 b5 b4 b3 b2 b1 b0

This means that an RGB image can be separated into:

Red channel

Green channel

Blue channel

and each channel can then be separated further into eight individual bit planes.

Instead of viewing the image normally, I treated the RGB values as binary data.

# **Conceptually:**

Normal RGB image
        ↓
Separate R / G / B channels
        ↓
Convert channel values to binary
        ↓
Inspect individual bit planes
        ↓
Look for structured information hidden in the apparent noise

This technique is known as bit-plane analysis and is commonly used in image steganography challenges.

Changing or arranging individual low-level bits of a pixel may have very little effect on how the image looks normally, while still 

allowing information to be hidden inside it.

# **Challenge Instance**

The challenge instance also provided an image.

The supplied challenge image helped indicate that the solution involved analyzing image colors and their underlying binary representation.

The instance image was then analyzed using the same RGB/bit-plane approach.

After separating and inspecting the relevant bit information, a readable message became visible:

ZDK MASTER OF CTF

The challenge description stated that the answer must be:

lowercase
words joined with underscores

##**Therefore:**

ZDK MASTER OF CTF

became:

master_of_ctf

 By submitting the Answer
 
I submitted:

master_of_ctf

to the private endpoint provided by the challenge instance.

The server accepted the phrase and returned the flag.

# 🚩 **Flag:**

zdk{MA5teR_OF_coLOR5_anD_C7F}

#**Concepts Used:**

RGB image representation

Image steganography

Bit-plane analysis

Binary representation of image pixels

Hidden information inside color channels
