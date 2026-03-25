# Day 36 — Bootstrap Carousel, Modal & Accordion

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 6 — Bootstrap
🧪 **Lab Experiments:** 28, 29

---

## Learning Objectives

By the end of this session, students will be able to:
- Build an image carousel (slideshow) with controls and captions
- Create modal (popup) dialogs with forms
- Build collapsible accordion (FAQ) sections
- Use Bootstrap's tooltip and toast components

---

## 1. Carousel (Slideshow)

```html
<div id="myCarousel" class="carousel slide" data-bs-ride="carousel">
    
    <!-- Indicators -->
    <div class="carousel-indicators">
        <button data-bs-target="#myCarousel" data-bs-slide-to="0" class="active"></button>
        <button data-bs-target="#myCarousel" data-bs-slide-to="1"></button>
        <button data-bs-target="#myCarousel" data-bs-slide-to="2"></button>
    </div>
    
    <!-- Slides -->
    <div class="carousel-inner">
        <div class="carousel-item active">
            <img src="https://via.placeholder.com/1200x400/0d6efd/ffffff?text=Slide+1" 
                 class="d-block w-100" alt="Slide 1">
            <div class="carousel-caption">
                <h5>First Slide</h5>
                <p>Welcome to Web Technology</p>
            </div>
        </div>
        <div class="carousel-item">
            <img src="https://via.placeholder.com/1200x400/198754/ffffff?text=Slide+2" 
                 class="d-block w-100" alt="Slide 2">
            <div class="carousel-caption">
                <h5>Second Slide</h5>
                <p>Learn Bootstrap Components</p>
            </div>
        </div>
        <div class="carousel-item">
            <img src="https://via.placeholder.com/1200x400/ffc107/000000?text=Slide+3" 
                 class="d-block w-100" alt="Slide 3">
            <div class="carousel-caption d-none d-md-block">
                <h5>Third Slide</h5>
                <p>Build responsive websites</p>
            </div>
        </div>
    </div>
    
    <!-- Controls -->
    <button class="carousel-control-prev" data-bs-target="#myCarousel" data-bs-slide="prev">
        <span class="carousel-control-prev-icon"></span>
    </button>
    <button class="carousel-control-next" data-bs-target="#myCarousel" data-bs-slide="next">
        <span class="carousel-control-next-icon"></span>
    </button>
</div>
```

### Carousel Options

| Attribute | Value | Purpose |
|-----------|-------|---------|
| `data-bs-ride="carousel"` | Auto-play |
| `data-bs-interval="3000"` | Slide every 3 seconds |
| `data-bs-ride="false"` | No auto-play |
| class `carousel-fade` | Fade transition instead of slide |

---

## 2. Modal (Popup Dialog)

```html
<!-- Trigger Button -->
<button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#myModal">
    Open Modal
</button>

<!-- Modal -->
<div class="modal fade" id="myModal" tabindex="-1">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title">Student Login</h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
            </div>
            <div class="modal-body">
                <form>
                    <div class="mb-3">
                        <label class="form-label">Email</label>
                        <input type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Password</label>
                        <input type="password" class="form-control">
                    </div>
                </form>
            </div>
            <div class="modal-footer">
                <button class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
                <button class="btn btn-primary">Login</button>
            </div>
        </div>
    </div>
</div>
```

### Modal Sizes

```html
<div class="modal-dialog modal-sm">...</div>   <!-- Small -->
<div class="modal-dialog">...</div>             <!-- Default -->
<div class="modal-dialog modal-lg">...</div>    <!-- Large -->
<div class="modal-dialog modal-xl">...</div>    <!-- Extra Large -->
<div class="modal-dialog modal-fullscreen">...</div> <!-- Fullscreen -->
```

---

## 3. Accordion (Collapsible Sections)

```html
<div class="accordion" id="faqAccordion">
    <div class="accordion-item">
        <h2 class="accordion-header">
            <button class="accordion-button" data-bs-toggle="collapse" 
                    data-bs-target="#faq1">
                What is Bootstrap?
            </button>
        </h2>
        <div id="faq1" class="accordion-collapse collapse show" 
             data-bs-parent="#faqAccordion">
            <div class="accordion-body">
                Bootstrap is a CSS framework that provides pre-built components
                and a responsive grid system for faster web development.
            </div>
        </div>
    </div>
    <div class="accordion-item">
        <h2 class="accordion-header">
            <button class="accordion-button collapsed" data-bs-toggle="collapse" 
                    data-bs-target="#faq2">
                Is Bootstrap free?
            </button>
        </h2>
        <div id="faq2" class="accordion-collapse collapse" 
             data-bs-parent="#faqAccordion">
            <div class="accordion-body">
                Yes! Bootstrap is completely free and open source under the MIT license.
            </div>
        </div>
    </div>
</div>
```

---

## 4. Tooltips & Toasts

### Tooltips

```html
<button class="btn btn-info" data-bs-toggle="tooltip" title="Hello from tooltip!">
    Hover me
</button>

<script>
// Initialize all tooltips
const tooltipTriggerList = document.querySelectorAll('[data-bs-toggle="tooltip"]');
const tooltipList = [...tooltipTriggerList].map(el => new bootstrap.Tooltip(el));
</script>
```

### Toasts (Notification popups)

```html
<div class="toast-container position-fixed top-0 end-0 p-3">
    <div class="toast" id="myToast">
        <div class="toast-header bg-success text-white">
            <strong class="me-auto">Success</strong>
            <small>Just now</small>
            <button type="button" class="btn-close btn-close-white" data-bs-dismiss="toast"></button>
        </div>
        <div class="toast-body">Form submitted successfully!</div>
    </div>
</div>

<script>
const toast = new bootstrap.Toast(document.getElementById('myToast'));
toast.show();
</script>
```

---

## Practical Session

### 🧪 Lab Experiments 28 & 29: Carousel, Modal & Accordion Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Bootstrap Components</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>

    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container">
            <a class="navbar-brand" href="#">🎓 MU — BCA</a>
            <div class="navbar-nav ms-auto">
                <button class="btn btn-outline-light btn-sm" data-bs-toggle="modal" 
                        data-bs-target="#loginModal">Login</button>
            </div>
        </div>
    </nav>

    <!-- Carousel -->
    <div id="heroCarousel" class="carousel slide carousel-fade" data-bs-ride="carousel" data-bs-interval="4000">
        <div class="carousel-indicators">
            <button data-bs-target="#heroCarousel" data-bs-slide-to="0" class="active"></button>
            <button data-bs-target="#heroCarousel" data-bs-slide-to="1"></button>
            <button data-bs-target="#heroCarousel" data-bs-slide-to="2"></button>
        </div>
        <div class="carousel-inner">
            <div class="carousel-item active">
                <div class="bg-primary text-white text-center" style="padding: 120px 0;">
                    <h1 class="display-4">Mandsaur University</h1>
                    <p class="lead">Empowering Minds, Transforming Futures</p>
                    <button class="btn btn-outline-light btn-lg">Learn More</button>
                </div>
            </div>
            <div class="carousel-item">
                <div class="bg-success text-white text-center" style="padding: 120px 0;">
                    <h1 class="display-4">BCA Program</h1>
                    <p class="lead">Build your career in Computer Applications</p>
                    <button class="btn btn-outline-light btn-lg">Apply Now</button>
                </div>
            </div>
            <div class="carousel-item">
                <div class="bg-info text-white text-center" style="padding: 120px 0;">
                    <h1 class="display-4">Web Technology</h1>
                    <p class="lead">Master HTML, CSS, JavaScript & Bootstrap</p>
                    <button class="btn btn-outline-light btn-lg">Start Learning</button>
                </div>
            </div>
        </div>
        <button class="carousel-control-prev" data-bs-target="#heroCarousel" data-bs-slide="prev">
            <span class="carousel-control-prev-icon"></span>
        </button>
        <button class="carousel-control-next" data-bs-target="#heroCarousel" data-bs-slide="next">
            <span class="carousel-control-next-icon"></span>
        </button>
    </div>

    <div class="container my-5">

        <!-- FAQ Accordion -->
        <h2 class="text-primary mb-4 text-center">Frequently Asked Questions</h2>
        <div class="accordion mb-5" id="faqAccordion">
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button class="accordion-button" data-bs-toggle="collapse" data-bs-target="#faq1">
                        What is Bootstrap?
                    </button>
                </h2>
                <div id="faq1" class="accordion-collapse collapse show" data-bs-parent="#faqAccordion">
                    <div class="accordion-body">
                        Bootstrap is a free, open-source CSS framework developed by Twitter. 
                        It includes pre-designed components, responsive grid, and JavaScript plugins 
                        that help developers build professional websites quickly.
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button class="accordion-button collapsed" data-bs-toggle="collapse" data-bs-target="#faq2">
                        Why use Bootstrap over plain CSS?
                    </button>
                </h2>
                <div id="faq2" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
                    <div class="accordion-body">
                        Bootstrap saves development time with its pre-built, tested components. 
                        It ensures cross-browser compatibility and provides a responsive grid system 
                        that handles different screen sizes automatically.
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button class="accordion-button collapsed" data-bs-toggle="collapse" data-bs-target="#faq3">
                        Is Bootstrap 5 different from Bootstrap 4?
                    </button>
                </h2>
                <div id="faq3" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
                    <div class="accordion-body">
                        Major changes: jQuery is no longer required, new utility API, 
                        improved grid system with xxl breakpoint, RTL support, 
                        updated forms, and new components like offcanvas.
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button class="accordion-button collapsed" data-bs-toggle="collapse" data-bs-target="#faq4">
                        How do I add Bootstrap to my project?
                    </button>
                </h2>
                <div id="faq4" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
                    <div class="accordion-body">
                        The easiest way is via CDN: add the Bootstrap CSS link in the 
                        <code>&lt;head&gt;</code> and the JS script before the closing 
                        <code>&lt;/body&gt;</code> tag. You can also download the files or 
                        use npm in larger projects.
                    </div>
                </div>
            </div>
        </div>

        <!-- Cards with Modal Triggers -->
        <h2 class="text-primary mb-4 text-center">Our Courses</h2>
        <div class="row g-4 mb-5">
            <div class="col-md-4">
                <div class="card shadow-sm h-100">
                    <div class="card-body text-center">
                        <div class="display-1 mb-3">🌐</div>
                        <h5 class="card-title">Web Technology</h5>
                        <p class="card-text">HTML, CSS, JS, Bootstrap</p>
                        <button class="btn btn-primary" data-bs-toggle="modal" 
                                data-bs-target="#courseModal1">Details</button>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card shadow-sm h-100">
                    <div class="card-body text-center">
                        <div class="display-1 mb-3">📊</div>
                        <h5 class="card-title">Data Structures</h5>
                        <p class="card-text">Arrays, Trees, Graphs</p>
                        <button class="btn btn-success" data-bs-toggle="modal" 
                                data-bs-target="#courseModal2">Details</button>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card shadow-sm h-100">
                    <div class="card-body text-center">
                        <div class="display-1 mb-3">🧮</div>
                        <h5 class="card-title">Mathematics</h5>
                        <p class="card-text">Discrete Math, Probability</p>
                        <button class="btn btn-warning" data-bs-toggle="modal" 
                                data-bs-target="#courseModal3">Details</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Login Modal -->
    <div class="modal fade" id="loginModal" tabindex="-1">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header bg-dark text-white">
                    <h5 class="modal-title">Student Login</h5>
                    <button class="btn-close btn-close-white" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <form>
                        <div class="form-floating mb-3">
                            <input type="email" class="form-control" id="loginEmail" placeholder="Email">
                            <label for="loginEmail">Email</label>
                        </div>
                        <div class="form-floating mb-3">
                            <input type="password" class="form-control" id="loginPwd" placeholder="Password">
                            <label for="loginPwd">Password</label>
                        </div>
                        <div class="form-check mb-3">
                            <input class="form-check-input" type="checkbox" id="remember">
                            <label class="form-check-label" for="remember">Remember me</label>
                        </div>
                    </form>
                </div>
                <div class="modal-footer">
                    <button class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
                    <button class="btn btn-primary">Login</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Course Detail Modals -->
    <div class="modal fade" id="courseModal1" tabindex="-1">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header bg-primary text-white">
                    <h5 class="modal-title">Web Technology — Details</h5>
                    <button class="btn-close btn-close-white" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <h6>Topics Covered:</h6>
                    <ul>
                        <li>Internet Technology & HTTP</li>
                        <li>HTML & HTML5</li>
                        <li>CSS & Responsive Design</li>
                        <li>JavaScript & DOM</li>
                        <li>Bootstrap Framework</li>
                    </ul>
                    <p><strong>Credits:</strong> 4 | <strong>Exam:</strong> 60 marks (theory) + 40 marks (practical)</p>
                </div>
                <div class="modal-footer">
                    <button class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="courseModal2" tabindex="-1">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header bg-success text-white">
                    <h5 class="modal-title">Data Structures — Details</h5>
                    <button class="btn-close btn-close-white" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <p>Arrays, Linked Lists, Stacks, Queues, Trees, Graphs, Sorting & Searching algorithms.</p>
                </div>
                <div class="modal-footer">
                    <button class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="courseModal3" tabindex="-1">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header bg-warning">
                    <h5 class="modal-title">Mathematics — Details</h5>
                    <button class="btn-close" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <p>Discrete Mathematics, Probability, Linear Algebra, Number Theory.</p>
                </div>
                <div class="modal-footer">
                    <button class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-dark text-white text-center py-3">
        <p class="mb-0">&copy; 2026 Mandsaur University</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

---

## Summary

| Component | Key Classes/Attributes |
|-----------|----------------------|
| Carousel | `carousel slide`, `carousel-inner`, `carousel-item` |
| Controls | `carousel-control-prev/next`, `data-bs-slide` |
| Modal | `modal fade`, `modal-dialog`, `modal-content` |
| Accordion | `accordion`, `accordion-item`, `accordion-collapse` |
| Tooltip | `data-bs-toggle="tooltip"`, `title="..."` |
| Toast | `toast`, `toast-header`, `toast-body` |

---

*Day 36 of 55 | Unit 6 — Bootstrap | Web Technology (25BCA060)*
