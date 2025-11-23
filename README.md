# Yogastic - Yoga & Wellness Website Template

![Deployment Status](https://img.shields.io/badge/deployment-active-success)
![HTML](https://img.shields.io/badge/HTML-69.5%25-orange)
![CSS](https://img.shields.io/badge/CSS-21.6%25-blue)
![JavaScript](https://img.shields.io/badge/JavaScript-8.7%25-yellow)

A modern, responsive website template designed for yoga studios, wellness centers, and health-focused businesses. Built with clean HTML, CSS, and JavaScript, featuring multiple layout options and a mobile-first design approach.

## 🌟 Live Demo

Visit the live website: [https://yogieats.in/](https://yogieats.in/)

## ✨ Features

- **Responsive Design**: Fully responsive layouts that work seamlessly across all devices
- **Multiple Page Layouts**: 
  - Single column
  - Two column
  - Three column
  - Three column with sidebar
  - Four column
  - Six column
- **Blog Features**:
  - Single post view
  - Infinite scroll
  - Load more pagination
- **Essential Pages**:
  - Home
  - About Us
  - Services
  - Pricing
  - FAQ
  - Team
  - Contact (with working PHP form)
- **Bootstrap Integration**: Built on Bootstrap framework for rapid development
- **Custom CSS**: Tailored styling for yoga and wellness aesthetics
- **JavaScript Functionality**: Interactive elements and smooth user experience

## 📁 Project Structure

```
yogieats/
├── index.html              # Homepage
├── about.html              # About page
├── services.html           # Services page
├── pricing.html            # Pricing page
├── faq.html                # FAQ page
├── team.html               # Team page
├── contact.html            # Contact page
├── contact-form.php        # Contact form handler
├── single-post.html        # Blog single post
├── infinite-scroll.html    # Infinite scroll blog
├── load-more.html          # Load more blog
├── one-column.html         # 1 column layout
├── two-column.html         # 2 column layout
├── three-column.html       # 3 column layout
├── three-colum-sidebar.html # 3 column with sidebar
├── four-column.html        # 4 column layout
├── six-column.html         # 6 column layout
├── bootstrap/              # Bootstrap framework files
├── css/                    # Custom stylesheets
├── js/                     # JavaScript files
├── images/                 # Image assets
├── Documentation/          # Template documentation
└── .github/workflows/      # GitHub Actions for deployment
```

## 🚀 Quick Start

### Prerequisites

- A web server (Apache, Nginx, or any static file server)
- PHP 7.0+ (if using contact form functionality)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/dhileep111/yogieats.git
```

2. Navigate to the project directory:
```bash
cd yogieats
```

3. Open `index.html` in your web browser or deploy to your web server.

### Contact Form Setup

The contact form requires PHP. Update the email configuration in `contact-form.php`:

```php
$to_email = "your-email@example.com"; // Change this to your email
```

## 🛠️ Technologies Used

- **HTML5**: Semantic markup
- **CSS3**: Modern styling with Flexbox and Grid
- **JavaScript**: Interactive functionality
- **Bootstrap**: Responsive framework
- **PHP**: Server-side form processing
- **GitHub Pages**: Automated deployment

## 📱 Responsive Breakpoints

- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

## 🎨 Customization

### Colors

Customize the color scheme by modifying variables in `css/style.css`:

```css
/* Primary colors */
--primary-color: #your-color;
--secondary-color: #your-color;
```

### Fonts

Update fonts in the CSS files or link new Google Fonts in the HTML head.

### Images

Replace images in the `images/` directory with your own content.

## 📄 Pages Overview

| Page | Description |
|------|-------------|
| Home | Main landing page with hero section |
| About | Company/studio information |
| Services | Yoga and wellness services offered |
| Pricing | Pricing plans and packages |
| FAQ | Frequently asked questions |
| Team | Team members showcase |
| Contact | Contact form and information |
| Blog | Various blog layout options |

## 🔧 Development

### Local Development

For local development with live reload, you can use:

```bash
# Using Python
python -m http.server 8000

# Or using Node.js
npx serve
```

Then visit `http://localhost:8000`

## 🌐 Deployment

This project is configured for automatic deployment to GitHub Pages.

### Manual Deployment

1. Push your changes to the `main` branch
2. GitHub Actions will automatically deploy to GitHub Pages
3. Your site will be live at `https://yourusername.github.io/yogieats`

### Custom Domain

To use a custom domain:
1. Add a `CNAME` file with your domain name
2. Configure DNS settings with your domain provider

## 📝 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Opera (latest)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Contact

For questions or support, please open an issue on GitHub.

## 📄 License

This project is available for personal and commercial use.

## 🙏 Acknowledgments

- Bootstrap framework
- Font Awesome icons
- Google Fonts

---

Built with ❤️ for the yoga and wellness community
