Seattle Love Broker — Landing Page
===================================
WordPress Integration Guide


FILES
-----
  index.html  — Complete standalone landing page (single file, no dependencies)
  tokens.css  — Extracted design tokens (reference only; tokens are embedded in index.html)


ASSETS USED (hosted externally)
-------------------------------
  These images are referenced via URL. For production, download and re-upload to your
  WordPress media library, then update the src attributes in index.html accordingly.

  1. Logo:
     https://mllovebroker.com/wp-content/uploads/2017/11/SLBlogo-scaled.jpg
     → Used in: <header class="nav"> — logo image

  2. About photo:
     https://mllovebroker.com/wp-content/uploads/2021/08/about-us.jpg
     → Used in: <section id="about"> — Monique Le portrait

  3. Couple photo:
     https://mllovebroker.com/wp-content/uploads/2018/01/couple_park.png
     → Used in: <section class="image-band"> — full-bleed couple walk


WORDPRESS SETUP — Option A: Custom Page Template
-------------------------------------------------
  1. In your theme directory, create a file: page-landing.php
  2. Add this header:
       <?php /* Template Name: Seattle Love Broker Landing */ ?>
  3. Paste the FULL index.html content below that header.
  4. Remove the <!DOCTYPE html>, <html>, <head>, and <body> tags — WordPress
     supplies these. Keep the <style> block and move it to wp_enqueue_style or
     inline it via wp_head.
  5. In WordPress admin → Pages → Add New → select the "Seattle Love Broker Landing"
     template from the Page Attributes panel.


WORDPRESS SETUP — Option B: Custom HTML Block
----------------------------------------------
  1. In WordPress admin → Pages → Add New.
  2. Add a "Custom HTML" block.
  3. Paste the contents of <body> from index.html (everything between <body> and </body>).
  4. Add the <style> block via the Theme Customizer → Additional CSS, or use a
     plugin like "Simple Custom CSS and JS" to inject the styles.
  5. Ensure your theme does not inject conflicting styles (padding, max-width, fonts).


FONTS
-----
  Google Fonts are loaded via <link> tag in the <head>:
  - Cormorant Garamond (display headings)
  - Crimson Pro (body text)

  If your WordPress theme already loads other fonts, the landing page fonts
  will still work independently — they are scoped by class names.


DESIGN DETAILS
--------------
  Macrostructure:  Letter (intimate, founder-led)
  Theme:           Custom luxury — cream paper + muted gold accent
  Nav:             N9 Edge-aligned minimal (logo left, CTA right)
  Footer:          Ft6 Letter close (signed off like a personal letter)
  Typography:      Cormorant Garamond (display) + Crimson Pro (body)
  Palette:         OKLCH-based warm cream / charcoal / gold
  Motion:          Scroll-reveal entrance, FAQ accordion
  Responsive:      Tested at 320 / 375 / 414 / 768 / 960 / 1440 px
  Accessibility:   Reduced-motion support, focus-visible outlines, semantic HTML


LINKS TO UPDATE
---------------
  These URLs point to the live WordPress site. Update if your domain changes:
  - https://mllovebroker.com/register/    → Registration / consultation page
  - https://mllovebroker.com/contact-us/  → Contact page
  - Social media links in the footer      → Facebook, X, Instagram, LinkedIn
