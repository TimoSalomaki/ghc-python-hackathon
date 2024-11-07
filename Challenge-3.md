# Photo Editor Challenge  
  
Welcome to the Photo Editor Challenge! You are tasked with enhancing a super bare-bones Python photo editor with essential functionalities. As the last developer on earth who can implement these features, your mission is to make this photo editor fully functional and user-friendly. Let's dive into the required enhancements.  

## Original code

```python
import tkinter as tk
from tkinter import filedialog, messagebox
from PIL import Image, ImageTk, ImageFilter

class PhotoEditor:
    def __init__(self, root):
        self.root = root
        self.root.title("Hackathon Photo Editor")
        self.root.geometry("800x600")
        self.root.resizable(False, False)

        self.image = None
        self.photo_image = None

        # Create GUI components
        self.create_widgets()

    def create_widgets(self):
        # Menu bar
        menubar = tk.Menu(self.root)
        file_menu = tk.Menu(menubar, tearoff=False)
        file_menu.add_command(label="Open", command=self.open_image)
        file_menu.add_command(label="Save As", command=self.save_image)
        file_menu.add_separator()
        file_menu.add_command(label="Exit", command=self.root.quit)
        menubar.add_cascade(label="File", menu=file_menu)

        self.root.config(menu=menubar)

        # Canvas to display the image
        self.canvas = tk.Canvas(self.root, width=800, height=500, bg="grey")
        self.canvas.pack()

        # Frame for buttons
        btn_frame = tk.Frame(self.root)
        btn_frame.pack(fill=tk.X, pady=10)

        # Grayscale button
        gray_btn = tk.Button(btn_frame, text="Grayscale", command=self.apply_grayscale)
        gray_btn.pack(side=tk.LEFT, padx=10)

        # Sepia button
        sepia_btn = tk.Button(btn_frame, text="Sepia", command=self.apply_sepia)
        sepia_btn.pack(side=tk.LEFT, padx=10)

        # Blur button
        blur_btn = tk.Button(btn_frame, text="Blur", command=self.apply_blur)
        blur_btn.pack(side=tk.LEFT, padx=10)

        # Reset button
        reset_btn = tk.Button(btn_frame, text="Reset", command=self.reset_image)
        reset_btn.pack(side=tk.RIGHT, padx=10)

    def open_image(self):
        file_path = filedialog.askopenfilename(
            filetypes=[("Image Files", "*.png;*.jpg;*.jpeg;*.bmp;*.gif")]
        )
        if file_path:
            self.image = Image.open(file_path)
            self.original_image = self.image.copy()
            self.display_image(self.image)

    def save_image(self):
        if self.image:
            file_path = filedialog.asksaveasfilename(
                defaultextension=".png",
                filetypes=[("PNG Files", "*.png"), ("JPEG Files", "*.jpg;*.jpeg")],
            )
            if file_path:
                self.image.save(file_path)
                messagebox.showinfo("Image Saved", "Your image has been saved successfully.")
        else:
            messagebox.showwarning("No Image", "Please open an image to save.")

    def display_image(self, img):
        img = img.resize((800, 500), Image.BICUBIC)
        self.photo_image = ImageTk.PhotoImage(img)
        self.canvas.create_image(400, 250, image=self.photo_image)

    def apply_grayscale(self):
        if self.image:
            self.image = self.image.convert("L").convert("RGB")
            self.display_image(self.image)
        else:
            messagebox.showwarning("No Image", "Please open an image to apply filters.")

    def apply_sepia(self):
        if self.image:
            sepia_image = self.image.convert("RGB")
            width, height = sepia_image.size

            pixels = sepia_image.load()  # Create the pixel map

            for py in range(height):
                for px in range(width):
                    r, g, b = sepia_image.getpixel((px, py))

                    # Apply sepia tone
                    tr = int(0.393 * r + 0.769 * g + 0.189 * b)
                    tg = int(0.349 * r + 0.686 * g + 0.168 * b)
                    tb = int(0.272 * r + 0.534 * g + 0.131 * b)

                    # Check for values > 255 and set to 255 if necessary
                    tr = min(255, tr)
                    tg = min(255, tg)
                    tb = min(255, tb)

                    pixels[px, py] = (tr, tg, tb)

            self.image = sepia_image
            self.display_image(self.image)
        else:
            messagebox.showwarning("No Image", "Please open an image to apply filters.")

    def apply_blur(self):
        if self.image:
            self.image = self.image.filter(ImageFilter.BLUR)
            self.display_image(self.image)
        else:
            messagebox.showwarning("No Image", "Please open an image to apply filters.")

    def reset_image(self):
        if self.image:
            self.image = self.original_image.copy()
            self.display_image(self.image)
        else:
            messagebox.showwarning("No Image", "Please open an image to reset.")

if __name__ == "__main__":
    root = tk.Tk()
    app = PhotoEditor(root)
    root.mainloop()
```
  
## Requirements  
  
### 1. Add Resizing  
**Why:** Because who doesn't like to stretch and squeeze their images? Resizing is like giving your photos a new wardrobe. Let users tailor the dimensions to fit their needs!  
  
### 2. Center the Image and Maintain Aspect Ratio When Window is Resized  
**Why:** Let's face it, nobody likes wonky, distorted images. Keep things classy by ensuring the image remains centered and maintains its aspect ratio when the window is resized. Think of it as keeping your photo editor on the straight and narrow.  
  
### 3. Show Scrollbars if the Image Doesn't Fit Inside the Window  
**Why:** When life gives you a massive image, give your users scrollbars. Navigating through large images should be as easy as scrolling through your Instagram feed.  
  
### 4. Speed Up the Resizing of the Window  
   - **Simple Way: Introducing Delay**  
   - **Better Way: Use More Performant Algorithm When Resizing**  
**Why:** Nobody has time for laggy windows. Speed up the resizing process to keep things snappy. A quick fix with a delay is like a band-aid, but a performant algorithm is the real superhero we need.  
  
### 5. Speed Up the Sepia Effect  
**Why:** Sepia is the OG of photo filters. Speed it up so users can instantly transport their images to the 19th century without waiting ages.  
  
### 6. Rotate the Image Left and Right 90 Degrees  
**Why:** Give your users the power to turn their world upside down (or at least their photos). Rotating images is a basic feature that can make a big difference in presentation.  
  
### 7. Flip the Image Horizontally and Vertically  
**Why:** Sometimes you just need to see things from a different perspective. Flipping images is like giving them a funhouse mirror treatment. It's basic, it's essential, and it's fun.  
  
### 8. Add Undo/Redo Functionality  
**Why:** Everyone makes mistakes, even the best of us. Undo/redo is like having a time machine for your edits. It lets users experiment without the fear of permanently messing things up.  
  
### 9. Add Brightness/Contrast Sliders  
   - **Make Sure That the Original Image is Not Irreversibly Modified**  
**Why:** Because nobody wants to turn their photo into a shadowy mess or a blinding light show. Brightness and contrast sliders give users precise control over their images. And remember: always preserve the original – it's like having a safety net for your edits.  
  
### 10. Add Functionality for Face Detection  
**Why:** Face detection is like adding a dash of AI magic. Whether it's for auto-enhancements or tagging, this feature makes your editor smarter and your users happier.  
  
### 11. Add an Emboss Effect  
**Why:** Give your images that fancy, carved-in-stone look with an emboss effect. It's like turning your photos into works of art – because who doesn't want to feel like Michelangelo?  
  
### 12. Add a Histogram  
**Why:** A histogram is like the X-ray of your image. It shows the hidden details of exposure and contrast, helping users fine-tune their photos like a pro.

### 13. What else?
Use your imagination!
