import React, { useState, useEffect } from 'react';

const ComprehensiveProfileReadme = () => {
  const [activeSection, setActiveSection] = useState('about');
  const [typedText, setTypedText] = useState('');
  const introText = "Software Engineer | Full Stack Developer | Tech Innovator";

  useEffect(() => {
    let currentIndex = 0;
    const typingEffect = setInterval(() => {
      if (currentIndex <= introText.length) {
        setTypedText(introText.slice(0, currentIndex));
        currentIndex++;
      } else {
        clearInterval(typingEffect);
      }
    }, 50);

    return () => clearInterval(typingEffect);
  }, []);

  const techSkills = [
    { name: "Languages", items: ["JavaScript", "Python", "TypeScript", "Java", "Go"] },
    { name: "Frontend", items: ["React", "Next.js", "Vue.js", "Tailwind CSS"] },
    { name: "Backend", items: ["Node.js", "Django", "Spring Boot", "GraphQL"] },
    { name: "DevOps", items: ["Docker", "Kubernetes", "AWS", "CI/CD"] }
  ];

  const projects = [
    {
      name: "AI-Powered Chatbot",
      description: "Machine learning chatbot with natural language processing",
      technologies: ["Python", "TensorFlow", "NLP"],
      link: "#"
    },
    {
      name: "Blockchain Voting Platform",
      description: "Secure, transparent voting system using blockchain",
      technologies: ["Solidity", "React", "Web3.js"],
      link: "#"
    },
    {
      name: "Cloud-Native Microservices",
      description: "Scalable microservices architecture for enterprise applications",
      technologies: ["Kubernetes", "Docker", "Go", "gRPC"],
      link: "#"
    }
  ];

  const experience = [
    {
      company: "Tech Innovations Inc.",
      role: "Senior Software Engineer",
      duration: "2021 - Present",
      highlights: [
        "Led development of scalable cloud infrastructure",
        "Implemented AI-driven feature optimization",
        "Mentored junior developers and conducted code reviews"
      ]
    },
    {
      company: "Digital Solutions LLC",
      role: "Full Stack Developer",
      duration: "2019 - 2021",
      highlights: [
        "Developed cross-platform mobile and web applications",
        "Improved system performance by 40%",
        "Implemented robust security protocols"
      ]
    }
  ];

  // SVG Icons
  const Icons = {
    GitHub: () => (
      <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
      </svg>
    ),
    Linkedin: () => (
      <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="currentColor">
        <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.784 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
      </svg>
    ),
    Twitter: () => (
      <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="currentColor">
        <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
      </svg>
    ),
    Zap: () => (
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
        <polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon>
      </svg>
    )
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 via-black to-indigo-900 text-white p-8 font-mono">
      <div className="max-w-6xl mx-auto relative space-y-8">
        {/* Header Section */}
        <header className="text-center relative">
          <div className="absolute -inset-0.5 bg-gradient-to-r from-blue-500 to-purple-600 rounded-xl blur-lg opacity-50 animate-pulse"></div>
          
          <div className="relative bg-black/70 rounded-xl border border-white/10 p-8">
            <h1 className="text-5xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-400 to-purple-600 mb-4">
              John Doe
            </h1>
            <p className="text-2xl text-gray-300 mb-4 min-h-[60px]">
              {typedText}
              <span className="animate-pulse">|</span>
            </p>
            
            {/* Social Links */}
            <div className="flex justify-center space-x-6 mt-6">
              <a href="#" className="hover:text-blue-400 transition-colors">
                <Icons.GitHub />
              </a>
              <a href="#" className="hover:text-blue-400 transition-colors">
                <Icons.Linkedin />
              </a>
              <a href="#" className="hover:text-blue-400 transition-colors">
                <Icons.Twitter />
              </a>
            </div>
          </div>
        </header>

        {/* Navigation Tabs */}
        <nav className="flex justify-center space-x-4 mb-8">
          {['About', 'Skills', 'Projects', 'Experience'].map((tab) => (
            <button
              key={tab}
              className={`px-4 py-2 rounded-lg transition-all duration-300 ${
                activeSection.toLowerCase() === tab.toLowerCase()
                  ? 'bg-blue-600 text-white'
                  : 'bg-white/10 hover:bg-white/20'
              }`}
              onClick={() => setActiveSection(tab.toLowerCase())}
            >
              {tab}
            </button>
          ))}
        </nav>

        {/* Rest of the component remains the same as in the previous version */}
        {/* ... (previous content) ... */}

        {/* In the Projects section, replace Zap with Icons.Zap */}
        <a 
          href={project.link} 
          className="text-blue-400 hover:underline flex items-center"
        >
          View Project <Icons.Zap />
        </a>
      </div>
    </div>
  );
};

export default ComprehensiveProfileReadme;
