# Python snippets


### Generating a test image

Generate a test image for test usage

```python
def get_test_image():
    """Returns an image for running tests
    """
    io_var = BytesIO()
    size = (10, 10)
    color = (255, 0, 0, 0)

    image = Image.new('RGBA', size, color)
    image.save(io_var, format='JPEG')
    image_file = InMemoryUploadedFile(
        io_var,
        None,
        'test.jpg',
        'jpeg',
        None,
        None
    )
    image_file.seek(0)

    return image_file
```