import React, { useState } from "react";
import { Button } from "/components/ui/button";
import { Input } from "/components/ui/input";
import { Textarea } from "/components/ui/textarea";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "/components/ui/card";

const Portfolio = () => {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [message, setMessage] = useState("");

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    // Form submission logic would go here
    console.log({ name, email, message });
    setName("");
    setEmail("");
    setMessage("");
  };

  const scrollToSection = (id: string) => {
    const element = document.getElementById(id);
    element?.scrollIntoView({ behavior: "smooth" });
  };

  return (
    <div className="min-h-screen bg-background text-foreground">
      {/* Navigation */}
      <nav className="fixed top-0 w-full bg-background/80 backdrop-blur-sm border-b border-border z-50">
        <div className="container mx-auto px-4 py-4">
          <div className="flex justify-between items-center">
            <h1 className="text-xl font-bold text-primary">Jane Doe</h1>
            <div className="hidden md:flex space-x-6">
              <button
                onClick={() => scrollToSection("hero")}
                className="text-foreground hover:text-primary transition-colors"
              >
                Home
              </button>
              <button
                onClick={() => scrollToSection("about")}
                className="text-foreground hover:text-primary transition-colors"
              >
                About
              </button>
              <button
                onClick={() => scrollToSection("projects")}
                className="text-foreground hover:text-primary transition-colors"
              >
                Projects
              </button>
              <button
                onClick={() => scrollToSection("skills")}
                className="text-foreground hover:text-primary transition-colors"
              >
                Skills
              </button>
              <button
                onClick={() => scrollToSection("contact")}
                className="text-foreground hover:text-primary transition-colors"
              >
                Contact
              </button>
            </div>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section id="hero" className="pt-32 pb-20 px-4">
        <div className="container mx-auto text-center">
          <div className="max-w-3xl mx-auto">
            <div className="w-32 h-32 mx-auto mb-6 rounded-full bg-primary/10 flex items-center justify-center">
              <svg
                className="w-20 h-20 text-primary"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  strokeLinecap="round"
                  strokeLinejoin="round"
                  strokeWidth={2}
                  d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"
                />
              </svg>
            </div>
            <h1 className="text-4xl md:text-6xl font-bold mb-4 text-foreground">
              Jane Doe
            </h1>
            <h2 className="text-xl md:text-2xl text-muted-foreground mb-8">
              Frontend Developer & UI/UX Designer
            </h2>
            <p className="text-lg text-muted-foreground mb-8">
              Crafting beautiful, responsive web experiences with modern
              technologies and user-centered design principles.
            </p>
            <div className="flex justify-center space-x-4">
              <Button onClick={() => scrollToSection("projects")}>
                View Work
              </Button>
              <Button variant="outline" onClick={() => scrollToSection("contact")}>
                Get In Touch
              </Button>
            </div>
          </div>
        </div>
      </section>

      {/* About Section */}
      <section id="about" className="py-20 px-4 bg-muted">
        <div className="container mx-auto">
          <div className="max-w-4xl mx-auto">
            <h2 className="text-3xl md:text-4xl font-bold text-center mb-12 text-foreground">
              About Me
            </h2>
            <div className="grid md:grid-cols-2 gap-8 items-center">
              <div>
                <img 
                  src="https://placeholder-image-service.onrender.com/image/400x400?prompt=Portrait of a professional female frontend developer working on laptop in modern office environment&id=about-portrait-01" 
                  alt="Professional portrait of a frontend developer working in a modern office setting" 
                  className="rounded-lg shadow-lg w-full"
                />
              </div>
              <div>
                <p className="text-muted-foreground mb-4">
                  I'm a passionate frontend developer with 5+ years of experience
                  creating modern web applications. I specialize in React,
                  TypeScript, and modern CSS frameworks while maintaining a
                  strong focus on user experience and accessibility.
                </p>
                <p className="text-muted-foreground mb-4">
                  My background in design allows me to bridge the gap between
                  visual design and technical implementation, ensuring that
                  every project I work on is both beautiful and functional.
                </p>
                <p className="text-muted-foreground">
                  When I'm not coding, you can find me exploring new design
                  trends, contributing to open source projects, or hiking in the
                  mountains to clear my mind.
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Projects Section */}
      <section id="projects" className="py-20 px-4">
        <div className="container mx-auto">
          <h2 className="text-3xl md:text-4xl font-bold text-center mb-12 text-foreground">
            Featured Projects
          </h2>
          <div className="grid md:grid-cols-3 gap-8">
            {/* Project 1 */}
            <Card className="overflow-hidden">
              <img 
                src="https://placeholder-image-service.onrender.com/image/400x250?prompt=E-commerce website dashboard with product listings, shopping cart, and user profile section&id=project-ecommerce-01" 
                alt="E-commerce dashboard interface showing product catalog and shopping cart functionality" 
                className="w-full h-48 object-cover"
              />
              <CardHeader>
                <CardTitle>E-Commerce Platform</CardTitle>
                <CardDescription>
                  Modern React e-commerce site with shopping cart and payment integration
                </CardDescription>
              </CardHeader>
              <CardContent>
                <p className="text-sm text-muted-foreground">
                  Built with React, TypeScript, and Stripe API. Features include
                  product filtering, user authentication, and order tracking.
                </p>
              </CardContent>
              <CardFooter>
                <Button variant="outline" className="w-full">
                  View Project
                </Button>
              </CardFooter>
            </Card>

            {/* Project 2 */}
            <Card className="overflow-hidden">
              <img 
                src="https://placeholder-image-service.onrender.com/image/400x250?prompt=Task management application with kanban board, calendar view, and productivity metrics&id=project-taskmanager-01" 
                alt="Task management application interface with kanban board and calendar integration" 
                className="w-full h-48 object-cover"
              />
              <CardHeader>
                <CardTitle>Task Management App</CardTitle>
                <CardDescription>
                  Collaborative project management tool with real-time updates
                </CardDescription>
              </CardHeader>
              <CardContent>
                <p className="text-sm text-muted-foreground">
                  Developed with Next.js, WebSockets, and PostgreSQL. Includes
                  drag-and-drop functionality and team collaboration features.
                </p>
              </CardContent>
              <CardFooter>
                <Button variant="outline" className="w-full">
                  View Project
                </Button>
              </CardFooter>
            </Card>

            {/* Project 3 */}
            <Card className="overflow-hidden">
              <img 
                src="https://placeholder-image-service.onrender.com/image/400x250?prompt=Weather application dashboard showing current conditions, forecast, and interactive maps&id=project-weather-01" 
                alt="Weather application interface with current conditions and multi-day forecast display" 
                className="w-full h-48 object-cover"
              />
              <CardHeader>
                <CardTitle>Weather Dashboard</CardTitle>
                <CardDescription>
                  Real-time weather application with interactive maps and alerts
                </CardDescription>
              </CardHeader>
              <CardContent>
                <p className="text-sm text-muted-foreground">
                  Built using Vue.js, Chart.js, and Weather API. Features
                  location-based forecasting and severe weather notifications.
                </p>
              </CardContent>
              <CardFooter>
                <Button variant="outline" className="w-full">
                  View Project
                </Button>
              </CardFooter>
            </Card>
          </div>
        </div>
      </section>

      {/* Skills Section */}
      <section id="skills" className="py-20 px-4 bg-muted">
        <div className="container mx-auto">
          <h2 className="text-3xl md:text-4xl font-bold text-center mb-12 text-foreground">
            Skills & Technologies
          </h2>
          <div className="grid md:grid-cols-4 gap-6 max-w-4xl mx-auto">
            <Card>
              <CardHeader>
                <CardTitle className="text-center">Frontend</CardTitle>
              </CardHeader>
              <CardContent className="text-center">
                <p className="text-muted-foreground">
                  React, Vue.js, TypeScript, JavaScript, HTML5, CSS3, Tailwind
                </p>
              </CardContent>
            </Card>

            <Card>
              <CardHeader>
                <CardTitle className="text-center">Backend</CardTitle>
              </CardHeader>
              <CardContent className="text-center">
                <p className="text-muted-foreground">
                  Node.js, Express, PostgreSQL, MongoDB, REST APIs, GraphQL
                </p>
              </CardContent>
            </Card>

            <Card>
              <CardHeader>
                <CardTitle className="text-center">Design</CardTitle>
              </CardHeader>
              <CardContent className="text-center">
                <p className="text-muted-foreground">
                  Figma, Adobe XD, UI/UX Design, Responsive Design, Accessibility
                </p>
              </CardContent>
            </Card>

            <Card>
              <CardHeader>
                <CardTitle className="text-center">Tools</CardTitle>
              </CardHeader>
              <CardContent className="text-center">
                <p className="text-muted-foreground">
                  Git, Docker, Webpack, Vite, Jest, CI/CD, AWS
                </p>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="py-20 px-4">
        <div className="container mx-auto">
          <div className="max-w-2xl mx-auto">
            <h2 className="text-3xl md:text-4xl font-bold text-center mb-12 text-foreground">
              Get In Touch
            </h2>
            <Card>
              <CardHeader>
                <CardTitle>Send me a message</CardTitle>
                <CardDescription>
                  I'm always interested in new opportunities and collaborations
                </CardDescription>
              </CardHeader>
              <CardContent>
                <form onSubmit={handleSubmit} className="space-y-4">
                  <div>
                    <Input
                      type="text"
                      placeholder="Your Name"
                      value={name}
                      onChange={(e) => setName(e.target.value)}
                      required
                    />
                  </div>
                  <div>
                    <Input
                      type="email"
                      placeholder="Your Email"
                      value={email}
                      onChange={(e) => setEmail(e.target.value)}
                      required
                    />
                  </div>
                  <div>
                    <Textarea
                      placeholder="Your Message"
                      rows={5}
                      value={message}
                      onChange={(e) => setMessage(e.target.value)}
                      required
                    />
                  </div>
                  <Button type="submit" className="w-full">
                    Send Message
                  </Button>
                </form>
              </CardContent>
            </Card>
            <div className="flex justify-center space-x-6 mt-8">
              <a href="#" className="text-primary hover:text-foreground transition-colors">
                <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
                </svg>
              </a>
              <a href="#" className="text-primary hover:text-foreground transition-colors">
                <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm-5 14H4v-6h11v6zm5 0h-3v-6h3v6zm0-8H4V6h16v4z"/>
                </svg>
              </a>
              <a href="#" className="text-primary hover:text-foreground transition-colors">
                <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M20 3H4a1 1 0 0 0-1 1v16a1 1 0 0 0 1 1h16a1 1 0 0 0 1-1V4a1 1 0 0 0-1-1zM8.339 18.337H5.667v-8.59h2.672v8.59zM7.003 8.574a1.548 1.548 0 1 1 0-3.096 1.548 1.548 0 0 1 0 3.096zm11.335 9.763h-2.669V14.16c0-.996-.018-2.277-1.388-2.277-1.39 0-1.601 1.086-1.601 2.207v4.248h-2.667v-8.59h2.56v1.174h.037c.355-.675 1.227-1.387 2.524-1.387 2.704 0 3.203 1.778 3.203 4.092v4.71z"/>
                </svg>
              </a>
              <a href="#" className="text-primary hover:text-foreground transition-colors">
                <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-8 px-4 border-t border-border">
        <div className="container mx-auto text-center">
          <p className="text-muted-foreground">
            © 2024 Jane Doe. Built with React and Tailwind CSS.
          </p>
        </div>
      </footer>
    </div>
  );
};

export default Portfolio;
