import cv2

def pixelate(image, pixel_size):
    # Get the dimensions of the image
    height, width = image.shape[:2]

    # Resize the image to a smaller size
    small_image = cv2.resize(image, (width // pixel_size, height // pixel_size), interpolation=cv2.INTER_LINEAR)

    # Enlarge the small image to the original size
    pixelated_image = cv2.resize(small_image, (width, height), interpolation=cv2.INTER_NEAREST)

    return pixelated_image

# Load the image
image = cv2.imread('WhatsApp Image 2023-11-13 at 9.07.51 PM.jpeg')

# Set the pixel size for the pixelation effect (adjust as needed)
pixel_size = 20

# Apply pixelation effect
pixelated_image = pixelate(image, pixel_size)

# Display the original and pixelated images
cv2.imshow('Original Image', image)
cv2.imshow('Pixelated Image', pixelated_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
