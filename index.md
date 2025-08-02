---
layout: default
title: Home
---
<!-- 1. HERO CAROUSEL & BOOKING WIDGET -->

<div class="hero-carousel-container">
<!-- Bootstrap Carousel -->
<div id="heroCarousel" class="carousel slide" data-bs-ride="carousel">
<div class="carousel-indicators">
<button type="button" data-bs-target="#heroCarousel" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
<button type="button" data-bs-target="#heroCarousel" data-bs-slide-to="1" aria-label="Slide 2"></button>
<button type="button" data-bs-target="#heroCarousel" data-bs-slide-to="2" aria-label="Slide 3"></button>
</div>
<div class="carousel-inner">
<div class="carousel-item active" style="background-image: url('/assets/images/hero-background1.jpg');">
<!-- == IMAGE REPLACEMENT ==
- Replace with a high-quality image of your lobby or exterior.
- Recommended Size: 1920x1080 pixels
-->
<div class="carousel-caption d-none d-md-block">
<h2>Unmatched Luxury & Service</h2>
<p>Experience a stay unlike any other.</p>
</div>
</div>
<div class="carousel-item" style="background-image: url('/assets/images/hero-background2.jpg');">
<!-- == IMAGE REPLACEMENT ==
- Replace with a high-quality image of a room with a view.
- Recommended Size: 1920x1080 pixels
-->
<div class="carousel-caption d-none d-md-block">
<h2>Rooms with Breathtaking Views</h2>
<p>Wake up to the beauty of the city.</p>
</div>
</div>
<div class="carousel-item" style="background-image: url('/assets/images/hero-background3.jpg');">
<!-- == IMAGE REPLACEMENT ==
- Replace with a high-quality image of your pool or another key amenity.
- Recommended Size: 1920x1080 pixels
-->
<div class="carousel-caption d-none d-md-block">
<h2>Relax and Unwind in Style</h2>
<p>Your perfect urban oasis awaits.</p>
</div>
</div>
</div>
<button class="carousel-control-prev" type="button" data-bs-target="#heroCarousel" data-bs-slide="prev">
<span class="carousel-control-prev-icon" aria-hidden="true"></span>
<span class="visually-hidden">Previous</span>
</button>
<button class="carousel-control-next" type="button" data-bs-target="#heroCarousel" data-bs-slide="next">
<span class="carousel-control-next-icon" aria-hidden="true"></span>
<span class="visually-hidden">Next</span>
</button>
</div>


<!-- Booking Widget -->

<div class="booking-widget">
<form class="row g-3 align-items-end">
<div class="col-md">
<label for="checkin" class="form-label">Check-in</label>
<input type="date" class="form-control" id="checkin">
</div>
<div class="col-md">
<label for="checkout" class="form-label">Check-out</label>
<input type="date" class="form-control" id="checkout">
</div>
<div class="col-md">
<label for="guests" class="form-label">Guests</label>
<select id="guests" class="form-select">
<option selected>1 Guest</option>
<option>2 Guests</option>
<option>3 Guests</option>
<option>4 Guests</option>
</select>
</div>
<div class="col-md-auto">
<button type="submit" class="btn btn-primary w-100">Check Availability</button>
</div>
</form>
</div>
</div>

<!-- 2. AMENITIES SECTION -->
<section id="amenities" class="text-center my-5 py-5" data-aos="fade-up">
<h2>Our Amenities</h2>
<p class="lead">We offer a wide range of amenities to make your stay exceptional.</p>
<div class="row mt-5">
{% for amenity in site.data.amenities %}
<div class="col-md-4 col-lg-2 mb-4">
<div class="amenity-item">
<div class="amenity-icon">
<i class="{{ amenity.icon }}"></i>
</div>
<h6>{{ amenity.name }}</h6>
</div>
</div>
{% endfor %}
</div>
</section>

<!-- 3. TESTIMONIALS SECTION -->

<section id="testimonials" class="testimonials-section bg-light my-5 py-5" data-aos="fade-up">
<div class="container">
<h2 class="text-center">What Our Guests Say</h2>
<div id="testimonialCarousel" class="carousel slide" data-bs-ride="carousel">
<div class="carousel-inner">
{% for testimonial in site.data.testimonials %}
<div class="carousel-item {% if forloop.first %}active{% endif %}">
<div class="testimonial-content">
<p class="testimonial-quote">"{{ testimonial.quote }}"</p>
<h5 class="testimonial-author">- {{ testimonial.author }}, {{ testimonial.location }}</h5>
</div>
</div>
{% endfor %}
</div>
<button class="carousel-control-prev" type="button" data-bs-target="#testimonialCarousel" data-bs-slide="prev">
<span class="carousel-control-prev-icon" aria-hidden="true"></span>
<span class="visually-hidden">Previous</span>
</button>
<button class="carousel-control-next" type="button" data-bs-target="#testimonialCarousel" data-bs-slide="next">
<span class="carousel-control-next-icon" aria-hidden="true"></span>
<span class="visually-hidden">Next</span>
</button>
</div>
</div>
</section>

<!-- 4. MEMBER BENEFITS SECTION -->

<section id="member-benefits" class="text-center my-5 py-5" data-aos="fade-up">
<div class="container">
<div class="row justify-content-center">
<div class="col-lg-8">
<div class="member-benefit-icon">
<i class="fas fa-crown"></i>
</div>
<h2>Become a Member</h2>
<p class="lead">Join our loyalty program to unlock exclusive benefits, including special rates, room upgrades, and members-only offers. Your loyalty deserves to be rewarded.</p>
<a href="#" class="btn btn-outline-primary btn-lg mt-3">Join Now & Save</a>
</div>
</div>
</div>
</section>

<!-- Rooms Section -->
<section id="rooms" class="my-5 py-5">
<div class="container">
<h2 class="text-center">Our Rooms & Suites</h2>
<p class="text-center lead">Here is a list of our beautifully appointed rooms. Choose the perfect space for your stay.</p>
<div class="row row-cols-1 row-cols-md-2 g-4 mt-4">
{% for room in site.rooms %}
<div class="col" data-aos="fade-up" data-aos-delay="{{ forloop.index0 | times: 100 }}">
<div class="card h-100 card-hover">
<img src="{{ room.image }}" class="card-img-top" alt="{{ room.title }}">
<div class="card-body d-flex flex-column">
<h5 class="card-title">{{ room.title }}</h5>
<p class="card-text">{{ room.excerpt }}</p>
<a href="{{ room.url }}" class="btn btn-primary mt-auto">View Details</a>
</div>
</div>
</div>
{% endfor %}
</div>
</div>
</section>

<!-- Offers Section -->
<section id="offers" class="bg-light my-5 py-5">
<div class="container">
<h2 class="text-center">Special Offers & Packages</h2>
<p class="text-center lead">Take advantage of our exclusive packages to make your stay even more memorable.</p>
<div class="row row-cols-1 row-cols-md-2 g-4 mt-4">
{% for offer in site.offers %}
<div class="col" data-aos="fade-up" data-aos-delay="{{ forloop.index0 | times: 100 }}">
<div class="card h-100 card-hover">
<img src="{{ offer.image }}" class="card-img-top" alt="{{ offer.title }}">
<div class="card-body d-flex flex-column">
<h5 class="card-title">{{ offer.title }}</h5>
<p class="card-text">{{ offer.excerpt }}</p>
<a href="{{ offer.url }}" class="btn btn-primary mt-auto">View Offer Details</a>
</div>
</div>
</div>
{% endfor %}
</div>
</div>
</section>

<!-- Gallery Section -->
<section id="gallery" class="my-5 py-5">
<div class="container">
<h2 class="text-center">Gallery</h2>
<p class="text-center lead">Explore the beauty and elegance of The Central Park Hotel.</p>
<div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4 mt-4">
<div class="col" data-aos="zoom-in">
<img src="/assets/images/rooms/standard-queen-card.jpg" class="img-fluid rounded shadow-sm" alt="Hotel Lobby">
</div>
<div class="col" data-aos="zoom-in" data-aos-delay="100">
<img src="/assets/images/rooms/deluxe-card.jpg" class="img-fluid rounded shadow-sm" alt="Room View">
</div>
<div class="col" data-aos="zoom-in" data-aos-delay="200">
<img src="/assets/images/rooms/classic-king-card.jpg" class="img-fluid rounded shadow-sm" alt="Restaurant">
</div>
</div>
</div>
</section>

<!-- Famous Places Section -->
<section id="famous-places" class="bg-light my-5 py-5">
<div class="container">
<h2 class="text-center">Famous Places in the City</h2>
<p class="text-center lead">Explore the most famous places in our city.</p>
<div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4 mt-4">
<div class="col" data-aos="zoom-in">
<img src="/assets/images/famous-places/placeholder1.jpg" class="img-fluid rounded shadow-sm" alt="Famous Place 1">
</div>
<div class="col" data-aos="zoom-in" data-aos-delay="100">
<img src="/assets/images/famous-places/placeholder2.jpg" class="img-fluid rounded shadow-sm" alt="Famous Place 2">
</div>
<div class="col" data-aos="zoom-in" data-aos-delay="200">
<img src="/assets/images/famous-places/placeholder3.jpg" class="img-fluid rounded shadow-sm" alt="Famous Place 3">
</div>
</div>
</div>
</section>

<!-- Blog Section -->
<section id="blog" class="my-5 py-5">
<div class="container">
<h2 class="text-center">Latest Posts</h2>
<div class="row">
<div class="col-lg-8 mx-auto">
{% for post in site.posts %}
<div class="card mb-4 shadow-sm" data-aos="fade-up">
<div class="card-body">
<h2 class="card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
<p class="card-text text-muted">{{ post.date | date: "%B %d, %Y" }}</p>
<p class="card-text">{{ post.excerpt }}</p>
<a href="{{ post.url | relative_url }}" class="btn btn-primary">Read More &rarr;</a>
</div>
</div>
{% endfor %}
</div>
</div>
</div>
</section>

<!-- Videos Section -->
<section id="videos" class="bg-light my-5 py-5">
<div class="container">
<h2 class="text-center">Our Videos</h2>
<div class="row">
<div class="col-lg-8 mx-auto">
<div class="ratio ratio-16x9 mb-4">
 <iframe width="560" height="315" src="https://www.youtube.com/embed/qemqQHaeCYo?si=rD5FCVzPx9eJAtxP" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
</div>
</div>
</div>
</section>

<!-- Location Section -->
<section id="location" class="my-5 py-5">
<div class="container">
<h2 class="text-center">Our Location</h2>
<p class="text-center lead">We are centrally located, providing easy access to the city's top attractions.</p>
<div class="row">
<div class="col-lg-8" data-aos="fade-up">
<!-- Google Maps Embed -->
<div class="ratio ratio-16x9 mb-4">
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3022.62954512527!2d-73.98235!3d40.74844!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c259a6f3b7ac8d%3A0x6b6a5a4a4b0c4e8!2s123%20Park%20Ave%2C%20New%20York%2C%20NY%2010001%2C%20USA!5e0!3m2!1sen!2sin!4v1620201655322!5m2!1sen!2sin" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
</div>
</div>
<div class="col-lg-4" data-aos="fade-up" data-aos-delay="100">
<div class="location-details">
<h3>The Central Park Hotel</h3>
<p>123 Park Avenue<br>New York, NY 10001</p>
</div>
</div>
</div>
<div class="row mt-5">
<div class="col-12" data-aos="fade-up">
<!-- "What's Nearby" Feature -->
<div class="nearby-container">
<ul class="nav nav-tabs" id="locationTab" role="tablist">
<li class="nav-item" role="presentation">
<button class="nav-link active" id="nearby-tab" data-bs-toggle="tab" data-bs-target="#nearby" type="button" role="tab" aria-controls="nearby" aria-selected="true">What's nearby</button>
</li>
<li class="nav-item" role="presentation">
<button class="nav-link" id="airports-tab" data-bs-toggle="tab" data-bs-target="#airports" type="button" role="tab" aria-controls="airports" aria-selected="false">Airports</button>
</li>
</ul>
<div class="tab-content" id="locationTabContent">
<div class="tab-pane fade show active" id="nearby" role="tabpanel" aria-labelledby="nearby-tab">
<ul class="list-group list-group-flush">
{% for item in site.data.nearby %}
<li class="list-group-item d-flex justify-content-between align-items-center">
<span><i class="fas fa-map-marker-alt me-2"></i>{{ item.name }}</span>
<span class="text-muted">{{ item.distance }}</span>
</li>
{% endfor %}
</ul>
</div>
<div class="tab-pane fade" id="airports" role="tabpanel" aria-labelledby="airports-tab">
<ul class="list-group list-group-flush">
<li class="list-group-item d-flex justify-content-between align-items-center">
<span><i class="fas fa-plane-departure me-2"></i>LaGuardia Airport (LGA)</span>
<span class="text-muted">8 miles</span>
</li>
<li class="list-group-item d-flex justify-content-between align-items-center">
<span><i class="fas fa-plane-departure me-2"></i>John F. Kennedy Airport (JFK)</span>
<span class="text-muted">15 miles</span>
</li>
</ul>
</div>
</div>
</div>
</div>
</div>
</div>
</section>

<!-- Contact Section -->
<section id="contact" class="bg-light my-5 py-5">
<div class="container">
<h2 class="text-center">Contact Us</h2>
<p class="text-center lead">We would love to hear from you. Please reach out with any questions or for reservation inquiries.</p>
<div class="row mt-5">
<div class="col-md-8 mx-auto" data-aos="fade-up">
<form>
<div class="mb-3">
<label for="name" class="form-label">Full Name</label>
<input type="text" class="form-control" id="name" required>
</div>
<div class="mb-3">
<label for="email" class="form-label">Email Address</label>
<input type="email" class="form-control" id="email" required>
</div>
<div class="mb-3">
<label for="message" class="form-label">Message</label>
<textarea class="form-control" id="message" rows="5" required></textarea>
</div>
<button type="submit" class="btn btn-primary">Send Message</button>
</form>
</div>
</div>
</div>
</section>
