# Personal Portfolio Website

A modern, responsive single-page CV website for Flutter Developer | Electrical Engineer.

## Features

- 🎨 **Modern Design**: Clean, professional layout with smooth animations
- 📱 **Fully Responsive**: Optimized for desktop, tablet, and mobile devices
- ⚡ **Fast Loading**: Optimized performance with minimal dependencies
- 🚀 **Smooth Scrolling**: Enhanced navigation between sections
- 🌙 **Semantic HTML5**: Proper structure using semantic elements
- 🎯 **SEO Friendly**: Optimized for search engines
- ♿ **Accessible**: WCAG compliant with proper focus states

## Sections

1. **Navigation**: Fixed navbar with smooth scrolling
2. **Hero/Header**: Introduction with call-to-action buttons
3. **About Me**: Background and experience description
4. **Skills**: Technology stack with icons and descriptions
5. **Projects**: Featured Flutter applications
6. **Education**: Academic background
7. **Contact**: Email, GitHub, and LinkedIn links
8. **Footer**: Copyright and social links

## Technologies Used

- **HTML5**: Semantic markup
- **CSS3**: Modern styling with Flexbox and CSS Grid
- **JavaScript**: Interactive functionality
- **Font Awesome**: Icons
- **Google Fonts**: Inter font family

## Customization Guide

### 1. Personal Information

Edit the following in `index.html`:

- **Name**: Replace "Your Name" with your actual name
- **Title**: Update "Flutter Developer | Electrical Engineer"
- **Email**: Change `mharba90@gmail.com` to your email
- **GitHub**: Update `github.com/mohammad-harba` with your GitHub profile
- **LinkedIn**: Update `linkedin.com/in/yourprofile` with your LinkedIn profile

### 2. About Section

Update the paragraphs in the About section to reflect your personal journey and experience.

### 3. Skills

Modify the skills cards to match your expertise:

- Update skill names and descriptions
- Change Font Awesome icons if needed
- Add or remove skill cards as necessary

### 4. Projects

Customize the project cards:

- Update project titles and descriptions
- Modify technology tags
- Add real GitHub and demo links
- Replace placeholder icons with actual project images

### 5. Education

Update the education section with:

- Your degree title
- University name
- Graduation year
- Relevant coursework

### 6. Colors and Styling

The main colors are defined in CSS variables. Key colors include:

- Primary: `#2563eb` (blue)
- Secondary: `#667eea` to `#764ba2` (gradient)
- Text: `#333` (dark gray)
- Background: `#ffffff` (white)

### 7. Adding a Profile Image

To add your profile photo:

1. Replace the `.profile-placeholder` div with an `<img>` tag
2. Add your image file to the project
3. Update the CSS accordingly

Example:

```html
<div class="hero-image">
  <img src="profile.jpg" alt="Your Name" class="profile-image" />
</div>
```

## File Structure

```
myWebsite/
├── index.html          # Main HTML file
├── styles.css          # CSS styles
├── script.js           # JavaScript functionality
└── README.md           # This file
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Performance Features

- Optimized images and icons
- Throttled scroll events
- Intersection Observer for animations
- Minimal JavaScript dependencies

## Deployment

This is a static website that can be deployed to:

- GitHub Pages
- Netlify
- Vercel
- Any web hosting service

Simply upload the files to your hosting provider's public directory.

## Local Development

1. Clone or download the files
2. Open `index.html` in a web browser
3. For live reloading during development, use a local server:

   ```bash
   # Using Python 3
   python -m http.server 8000

   # Using Node.js (with http-server package)
   npx http-server
   ```

## Customization Tips

1. **Icons**: Browse Font Awesome for different icons
2. **Colors**: Use tools like Coolors.co for color palette inspiration
3. **Fonts**: Google Fonts offers many professional font options
4. **Images**: Use high-quality, optimized images for better performance
5. **Content**: Keep descriptions concise and impactful

## License

This template is free to use and modify for personal and commercial projects.

---

**Note**: Remember to replace all placeholder content with your actual information before deploying the website!

## Work Experience

### Domethics

- **Field**: Internet of Things (IoT)
- **Role**: Worked on innovative IoT solutions, bridging hardware and software to create smart, connected devices.
