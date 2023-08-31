/**
 * 
 * Manipulating the DOM exercise.
 * Exercise programmatically builds navigation,
 * scrolls to anchors from navigation,
 * and highlights section in viewport upon scrolling.
 * 
 * Dependencies: None
 * 
 * JS Version: ES2015/ES6
 * 
 * JS Standard: ESlint
 * 
*/

/**
 * Comments should be present at the beginning of each procedure and class.
 * Great to have comments before crucial code sections within the procedure.
*/

/**
 * Define Global Variables
 * 
*/
// Add an event listener to execute code once the DOM content is loaded
// Add an event listener to execute code once the DOM content is loaded
document.addEventListener("DOMContentLoaded", function () {
  const sections = document.querySelectorAll("section"); // Select all sections
  const navList = document.getElementById("navbar__list"); // Select the navbar list

  // Loop through each section and create a corresponding navigation link
  //each link connects to the page it corresponds with
  sections.forEach((section, index) => {
    //creates new html anchor
    const navLink = document.createElement("a");
    //sets text to new anchor
    navLink.textContent = section.getAttribute("data-nav");
    //sets link to corresponding page
    navLink.href = `#section${index + 1}`;
    //calls navlink to menu link
    navLink.classList.add("menu__link");

//generates a navigation link for each section
    const listItem = document.createElement("li");
    listItem.appendChild(navLink);
    navList.appendChild(listItem);
  });

  // Smooth scroll when clicking on navigation links
  const navLinks = document.querySelectorAll(".menu__link");
  navLinks.forEach((link) => {
    //listener that allows clicking the linked elements
    link.addEventListener("click", (event) => {
      event.preventDefault();
      const targetSection = document.querySelector(link.getAttribute("href"));
      //behavior listed below allows for smooth rolling of the page after clicking a link
      targetSection.scrollIntoView({ behavior: "smooth" });
    });
  });

  // Add the "your-active-class" to the section currently in view
  //ensures proper page is highlighted when clicked
  function setActiveSection() {
    sections.forEach((section) => {
      const rect = section.getBoundingClientRect();
      if (rect.top >= 0 && rect.top <= window.innerHeight) {
        section.classList.add("your-active-class");
      } else {
        section.classList.remove("your-active-class");
      }
    });
  }

  // Listen for scroll events and update the active section accordingly
  window.addEventListener("scroll", setActiveSection);

  // Initialize the active section on page load
  setActiveSection();
});
