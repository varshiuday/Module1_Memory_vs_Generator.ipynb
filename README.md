# Choose the first non-agri image
dir_non_agri = './images_dataSAT/class_0_non_agri/'
first_image_file = os.listdir(dir_non_agri)[0]
image_path = os.path.join(dir_non_agri, first_image_file)

# Load image and convert to array
image_data = np.array(Image.open(image_path))
print("Shape of the image:", image_data.shape)
images = os.listdir(dir_non_agri)[:4]

plt.figure(figsize=(10, 3))
for i, img_file in enumerate(images):
    img = Image.open(os.path.join(dir_non_agri, img_file))
    plt.subplot(1, 4, i+1)
    plt.imshow(img)
    plt.axis('off')
plt.show()
dir_agri = './images_dataSAT/class_1_agri/'
agri_images_paths = sorted([os.path.join(dir_agri, f) for f in os.listdir(dir_agri)])
print("First 5 agricultural image paths:", agri_images_paths[:5])
num_agri_images = len(os.listdir(dir_agri))
print("Number of agricultural images:", num_agri_images)
images_agri = os.listdir(dir_agri)[:4]

plt.figure(figsize=(10, 3))
for i, img_file in enumerate(images_agri):
    img = Image.open(os.path.join(dir_agri, img_file))
    plt.subplot(1, 4, i+1)
    plt.imshow(img)
    plt.axis('off')
plt.show()
