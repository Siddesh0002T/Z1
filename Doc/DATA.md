# Content Registry & Structured Data Store
## Creative Developer 3D Editorial Portfolio

---

## 1. Developer Identity & Bio Data

```json
{
  "name": "Siddhesh More",
  "role": "Web & Mobile Developer",
  "location": "Nashik, Maharashtra, India",
  "availability": "Available for full-time roles, contracts & creative commissions",
  "experienceYears": "4+",
  "projectsCompleted": "30+",
  "technologiesCount": "15+",
  "bio": "Based in India. I'm a web and mobile developer with knowledge in HTML, CSS, Java, JavaScript, PHP, MySQL, and more. I enjoy learning new technologies and creating.",
  "disciplines": [
    {
      "icon": "⬡",
      "title": "Web Development",
      "description": "Building performant and accessible web applications using HTML, CSS, JavaScript, and modern frameworks."
    },
    {
      "icon": "◈",
      "title": "Mobile App Development",
      "description": "Crafting responsive and interactive mobile experiences utilizing Java, Kotlin, and cross-platform tools."
    },
    {
      "icon": "◉",
      "title": "Backend & Database",
      "description": "Designing scalable server-side systems and managing data with PHP, Node.js, and MySQL databases."
    }
  ]
}
```

---

## 2. Projects Data Store

```typescript
export const PROJECTS = [
  {
    id: 1,
    title: 'Nex-Mind',
    tagline: 'Ai Working.',
    description: 'Next-generation AI interaction platform exploring cognitive interfaces and real-time inference workflows.',
    tech: ['JavaScript', 'AI APIs', 'Node.js'],
    image: '/images/project1.jpg',
    link: 'https://github.com/Siddesh0002T/Nex-Mind',
    github: 'https://github.com/Siddesh0002T/Nex-Mind',
    featured: true
  },
  {
    id: 2,
    title: 'FixMate',
    tagline: 'FixMate Working On It.',
    description: 'On-demand service booking and maintenance utility application engineered with robust TypeScript architecture.',
    tech: ['TypeScript', 'Next.js', 'Tailwind CSS'],
    image: '/images/project2.jpg',
    link: 'https://github.com/Siddesh0002T/FixMate',
    github: 'https://github.com/Siddesh0002T/FixMate',
    featured: true
  },
  {
    id: 3,
    title: 'OIBSIP',
    tagline: 'Oasis Infobyte Internship Program',
    description: 'Comprehensive software development task submissions, interactive web utilities, and projects built during the Oasis Infobyte Student Internship Program.',
    tech: ['JavaScript', 'HTML5', 'CSS3'],
    image: '/images/project3.jpg',
    link: 'https://github.com/Siddesh0002T/OIBSIP',
    github: 'https://github.com/Siddesh0002T/OIBSIP',
    featured: false
  }
];
```

---

## 3. Professional Experience Data Store

```typescript
export const EXPERIENCES = [
  {
    id: 'rubbysoft',
    role: 'Full-stack Developer',
    company: 'RubbySoft',
    date: 'Jul 2024 - Present',
    location: 'Remote',
    description: 'Developing scalable web applications using React, Node.js, and PHP. Leading project management and problem solving across 30+ engineering skills.',
    skills: 'Project Management, Problem Solving, React, Node.js, PHP'
  },
  {
    id: 'netleap',
    role: 'Web Development Intern',
    company: 'NetLeap IT Training',
    date: 'May 2024 - Jun 2024',
    location: 'On-site',
    description: 'Built responsive front-end designs using HTML, CSS, JavaScript, ensuring accessible User Interface Design and cross-browser consistency.',
    skills: 'User Interface Design, HTML, CSS, JavaScript'
  }
];
```

---

## 4. Academic Credentials & Education

```typescript
export const EDUCATIONS = [
  {
    id: 'be',
    degree: 'BE in Computer Engineering',
    college: 'JIT Nashik',
    date: '2022 - 2025',
    affiliation: 'SPPU (Savitribai Phule Pune University)',
    description: 'Bachelor of Engineering in Computer Engineering. Focused on advanced software development, data structures, algorithms, system architecture, and modern web technologies.',
    skills: 'Algorithms, Architecture, Web Dev, Programming'
  },
  {
    id: 'diploma',
    degree: 'Diploma in Computer Eng.',
    college: 'Mahavir Polytechnic',
    date: '2019 - 2022',
    affiliation: 'MSBTE (Maharashtra State Board of Technical Education)',
    description: 'Graduated with a Diploma in Computer Engineering. Built a strong foundation in computer science principles, database management, and networking.',
    skills: 'Database, Networking, Fundamentals, Programming'
  }
];
```

---

## 5. Skills Taxonomy & Proficiency Registry

### 5.1 Category Groupings

```typescript
export const SKILL_CATEGORIES = [
  {
    category: 'Frontend',
    skills: [
      { name: 'HTML5 & CSS3', level: 95, color: '#E34F26', description: 'Semantic structure and modern responsive styling.' },
      { name: 'JavaScript', level: 90, color: '#F7DF1E', description: 'Dynamic web interactions and frontend logic.' },
      { name: 'React / Next.js', level: 85, color: '#00d4ff', description: 'Component-driven UI architecture with hooks and state management.' },
      { name: 'TypeScript', level: 80, color: '#3178C6', description: 'Static typing for robust and scalable applications.' }
    ]
  },
  {
    category: 'Backend & DB',
    skills: [
      { name: 'PHP', level: 85, color: '#777BB4', description: 'Server-side scripting and backend logic.' },
      { name: 'Java', level: 80, color: '#007396', description: 'Enterprise-grade backend systems and APIs.' },
      { name: 'MySQL', level: 88, color: '#4479A1', description: 'Relational database design and query optimization.' },
      { name: 'Node.js', level: 82, color: '#00ff41', description: 'Scalable event-driven backend services.' }
    ]
  },
  {
    category: 'Mobile & Cloud',
    skills: [
      { name: 'Android / Kotlin', level: 85, color: '#3DDC84', description: 'Native mobile application development.' },
      { name: 'Flutter', level: 75, color: '#02569B', description: 'Cross-platform mobile and web applications.' },
      { name: 'Firebase', level: 80, color: '#FFCA28', description: 'Realtime database, authentication, and cloud functions.' },
      { name: 'AWS / Cloudflare', level: 70, color: '#FF9900', description: 'Cloud infrastructure and deployment automation.' }
    ]
  }
];
```

### 5.2 Detailed Radar Skills Matrix

```typescript
export const DETAILED_SKILLS = [
  { name: 'React', category: 'FRONTEND', percentage: 95, color: '#61DAFB' },
  { name: 'Next.js', category: 'FULLSTACK', percentage: 90, color: '#FFFFFF' },
  { name: 'Three.js', category: 'WEBGL', percentage: 85, color: '#FFFFFF' },
  { name: 'GSAP', category: 'MOTION', percentage: 92, color: '#88CE02' },
  { name: 'Node.js', category: 'BACKEND', percentage: 88, color: '#68A063' },
  { name: 'Python', category: 'BACKEND', percentage: 82, color: '#FFD43B' },
  { name: 'TypeScript', category: 'FRONTEND', percentage: 94, color: '#3178C6' }
];
```

---

## 6. Social Channels & Contact Endpoints

```json
{
  "github": "https://github.com/Siddesh0002T",
  "linkedin": "https://linkedin.com/in/siddhesh0002t",
  "twitter": "https://twitter.com/siddhesh0002t",
  "stackoverflow": "https://stackoverflow.com/users/24676320/siddhesh-more",
  "orcid": "https://orcid.org/0009-0008-5855-0909",
  "email": "siddhesh0002t@example.com"
}
```

---

## 7. 3D Model & Public Asset Manifest

| Asset Path | File Type | Size | Role / Usage |
| :--- | :--- | :--- | :--- |
| `/card.glb` | 3D GLTF Binary | ~654 KB | Base 3D geometry of the ID badge with UV texture coordinates. |
| `/lanyard.png` | PNG Image | ~350 KB | High-contrast woven lanyard strap texture with repeating typography. |
| `/lanyard2.png`| PNG Image | ~2.6 MB | Alternative high-definition woven strap texture. |
| `/images/profile.png` | PNG Alpha Image | ~660 KB | Cutout studio portrait of Siddhesh More used for the Hero glide sequence. |
| `/images/profilewithbg.jpeg`| JPEG Image | ~293 KB | Source photo with background used for ASCII art generation in `ASCIIPortrait`. |
