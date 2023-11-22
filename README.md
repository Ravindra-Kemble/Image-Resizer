# Image-Resizer
#Enter the Image-File 
file_name = "farari_car.jpg"
image = Image.open(file_name)
# Resize the image
def resized_image(image, new_width, new_height):
    image = image.resize((new_width, new_height))
    print(f"The Size of Resized Image is {image.size}")
    print(image.show())
    choice = input("Save?, Y or N: ").lower()
    if choice == "y":
        image.save(f"Resized_{file_name}")
    else:
        pass
def resized_image_by_percent(image, scale_percent):
    dimension = image.size
    width = int(dimension[0]*scale_percent / 100)
    height = int(dimension[1]*scale_percent / 100)
    image = image.resize((width, height))
    print(f"The Size of Resized Image is {(width, height)}")
    print(image.show())
    if choice == "y":
        image.save("Resized_farari_car.jpg")
    else:
        pass
print(f"The mode of the image is {image.mode}")
print(f"The Size of the image is {image.size}")
Option = input("Choose the method to resize the photo, A = Dimension, B= By Percent.\n").lower()
if Option  == 'a':
    width = int(input("Width: "))
    height = int(input("Height: "))
    resized_image(image, width, height)
else:
    scale_percent = int(input("What percent would you like to reduse the size of image?\n"))
    resized_image_by_percent(image, scale_percent)
    choice = input("Save?, Y or N: ").lower()
