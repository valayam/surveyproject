# ValayathilSurveyFrontend

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.

## Project Setup and Features

### 1. Created a Landing Page Component

- Generated a new component for the landing page:
  ```sh
  ng generate component landing-page
  ```

- Added HTML template for the landing page in `landing-page.component.html`:
  ```html
  <header>
      <div class="logo">My Website</div>
      <nav>
          <ul>
              <li><a routerLink="/">Home</a></li>
              <li><a routerLink="/about">About</a></li>
              <li>
                  <a routerLink="/services">Services</a>
                  <ul>
                      <li><a routerLink="/services/web-design">Web Design</a></li>
                      <li><a routerLink="/services/seo">SEO</a></li>
                      <li><a routerLink="/services/marketing">Marketing</a></li>
                  </ul>
              </li>
              <li><a routerLink="/contact">Contact</a></li>
          </ul>
      </nav>
      <div class="auth-links">
          <a routerLink="/login">Login</a>
          <a routerLink="/register">Register</a>
      </div>
  </header>
  <footer>
      &copy; 2023 My Website. All rights reserved.
  </footer>
  ```

- Added CSS styles for the landing page in `landing-page.component.css`:
  ```css
  body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
  }
  header {
      background-color: #333;
      color: white;
      padding: 10px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
  }
  header .logo {
      font-size: 24px;
  }
  nav ul {
      list-style-type: none;
      margin: 0;
      padding: 0;
      display: flex;
  }
  nav ul li {
      position: relative;
  }
  nav ul li a {
      color: white;
      padding: 10px 20px;
      text-decoration: none;
      display: block;
  }
  nav ul li a:hover {
      background-color: #575757;
  }
  nav ul li ul {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      background-color: #333;
      padding: 0;
  }
  nav ul li:hover ul {
      display: block;
  }
  nav ul li ul li a {
      padding: 10px;
  }
  .auth-links a {
      color: white;
      padding: 10px 20px;
      text-decoration: none;
  }
  .auth-links a:hover {
      background-color: #575757;
  }
  footer {
      background-color: #333;
      color: white;
      text-align: center;
      padding: 10px 0;
      position: fixed;
      width: 100%;
      bottom: 0;
  }
  ```

### 2. Set Up Routing

- Generated components for different pages:
  ```sh
  ng generate component home
  ng generate component about
  ng generate component services
  ng generate component contact
  ng generate component login
  ng generate component register
  ```

- Defined routes in `app-routing.module.ts`:
  ```typescript
  import { NgModule } from '@angular/core';
  import { RouterModule, Routes } from '@angular/router';
  import { HomeComponent } from './home/home.component';
  import { AboutComponent } from './about/about.component';
  import { ServicesComponent } from './services/services.component';
  import { ContactComponent } from './contact/contact.component';
  import { LoginComponent } from './login/login.component';
  import { RegisterComponent } from './register/register.component';

  const routes: Routes = [
    { path: '', component: HomeComponent },
    { path: 'about', component: AboutComponent },
    { path: 'services', component: ServicesComponent },
    { path: 'contact', component: ContactComponent },
    { path: 'login', component: LoginComponent },
    { path: 'register', component: RegisterComponent },
  ];

  @NgModule({
    imports: [RouterModule.forRoot(routes)],
    exports: [RouterModule]
  })
  export class AppRoutingModule { }
  ```

- Updated navigation links in `landing-page.component.html` to use `routerLink`:
  ```html
  <header>
      <div class="logo">My Website</div>
      <nav>
          <ul>
              <li><a routerLink="/">Home</a></li>
              <li><a routerLink="/about">About</a></li>
              <li>
                  <a routerLink="/services">Services</a>
                  <ul>
                      <li><a routerLink="/services/web-design">Web Design</a></li>
                      <li><a routerLink="/services/seo">SEO</a></li>
                      <li><a routerLink="/services/marketing">Marketing</a></li>
                  </ul>
              </li>
              <li><a routerLink="/contact">Contact</a></li>
          </ul>
      </nav>
      <div class="auth-links">
          <a routerLink="/login">Login</a>
          <a routerLink="/register">Register</a>
      </div>
  </header>
  <footer>
      &copy; 2023 My Website. All rights reserved.
  </footer>
  ```

- Included the router outlet in `app.component.html`:
  ```html
  <router-outlet></router-outlet>
  ```

### 3. Pushed Changes to GitHub

- Initialized a Git repository:
  ```sh
  git init
  ```

- Added all files to the staging area:
  ```sh
  git add .
  ```

- Committed the changes:
  ```sh
  git commit -m "Add landing page component with routing"
  ```

- Added the remote repository URL:
  ```sh
  git remote add origin https://github.com/yourusername/your-repo.git
  ```

- Pushed the changes to the remote repository:
  ```sh
  git push -u origin master
  ```

Replace `https://github.com/yourusername/your-repo.git` with your actual GitHub repository URL. This summary documents the steps taken to set up the landing page and routing in the Angular application.
```