document.addEventListener('DOMContentLoaded', function() {
    const skillsSection = document.getElementById('skills');
    const skillElements = document.querySelectorAll('.skills-grid .skill');

    function animateSkills() {
        skillElements.forEach((skill, index) => {
            skill.style.animationDelay = `${index * 0.1}s`;
            skill.classList.add('animated-skill');
        });
    }

    function resetSkillsAnimation() {
        skillElements.forEach(skill => {
            skill.classList.remove('animated-skill');
        });
    }

    // Trigger animation when entering the skills section
    window.addEventListener('scroll', function() {
        const skillsSectionTop = skillsSection.getBoundingClientRect().top;
        const windowHeight = window.innerHeight;

        if (skillsSectionTop < windowHeight) {
            resetSkillsAnimation(); // Reset animation before applying again
            animateSkills();
        }
    });
});
