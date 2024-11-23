"use client";
import React from "react";

function MainComponent() {
  const [selectedField, setSelectedField] = useState(null);
  const [searchTerm, setSearchTerm] = useState("");
  const [hoveredCourse, setHoveredCourse] = useState(null);

  const fields = {
    mechanical: {
      title: "Mechanical Engineering",
      courses: [
        {
          name: "Thermodynamics",
          link: "https://youtu.be/pMmHdWvN_FI?list=PLyqSpQzTE6M_QOKxVxZ5nQ48gOkzg7zWP",
        },
        {
          name: "Fluid Mechanics",
          link: "https://youtu.be/YjngEKMR2V4?list=PLWPirh4EWFpGR5kjvxk_ZqopOtwdqS_uR",
        },
        {
          name: "Machine Design",
          link: "https://youtu.be/nqhyCzrFp1s",
        },
        {
          name: "Advanced Manufacturing",
          link: "https://youtu.be/6ysDAmtF_uU?list=PLsp7GVN6lOq2Qt9Iyl5xjY42ez1r_exC3",
        },
        {
          name: "Robotics",
          link: "https://youtu.be/rYWJdZ5qg6M?list=PLbRMhDVUMngcdUbBySzyzcPiFTYWr4rV_",
        },
        {
          name: "Mechatronics",
          link: "https://youtu.be/zVVITxiec7g?list=PLLy_2iUCG87BNHXRb6L2pWEpMcLoFaY_U",
        },
      ],
      icon: "fa-cogs",
    },
    civil: {
      title: "Civil Engineering",
      courses: [
        {
          name: "Structural Analysis",
          link: "https://youtu.be/nNsV395omjY?list=PL6nIzK-h0nVXKypaeuF0eL2QSUezMnEgk",
        },
        {
          name: "Geotechnical Engineering",
          link: "https://youtu.be/afirGWlleSM?list=PL3MO67NH2XxJytJh5pAKKSIm5k4MWGicO",
        },
        {
          name: "Hydraulics",
          link: "https://youtu.be/tmzInxHyyFk?list=PLbRMhDVUMngdInIhHKoECcrz27t_MJvD4",
        },
        {
          name: "Earthquake Engineering",
          link: "https://youtu.be/q-kHDw37XOM?list=PLbMVogVj5nJRNzx4KtSTVj7qr9OxwY3IF",
        },
        {
          name: "Building Information Modeling",
          link: "https://youtu.be/HHGWLuxXSMI?list=PLzUQqiz9J7vF73FPgLZMUpkU4jl_mRa-b",
        },
      ],
      icon: "fa-building",
    },
    electronics: {
      title: "Electronic Engineering",
      courses: [
        {
          name: "Circuit Analysis",
          link: "https://youtu.be/S9fMd1cH9ik?list=PLX2gX-ftPVXWv1eWntPcZtztrmwYBiBQY",
        },
        {
          name: "Embedded Systems",
          link: "https://youtu.be/TP1_F3IVjBc?list=PLJ5C_6qdAvBEUjcu1ka0QY9G-zoOlXqCL",
        },
        {
          name: "Microelectronics",
          link: "https://youtu.be/366BVdmcUxk?list=PLLy_2iUCG87C-GS7B4vJ37Iz3fevmYU1h",
        },
        {
          name: "Signal Processing",
          link: "https://youtu.be/z3smaAYXYgc?list=PL-DDW8QIRjNO5h384HWnSnv2Uc9p-l1of",
        },
        {
          name: "VLSI Design",
          link: "https://youtu.be/9Q9yIyNiAJQ?list=PLrjkTql3jnm8CKYCF0ZHyEFnaL-Homy97",
        },
        {
          name: "IoT Applications",
          link: "https://youtu.be/h0gWfVCSGQQ",
        },
      ],
      icon: "fa-microchip",
    },
    computer: {
      title: "Computer Engineering",
      courses: [
        {
          name: "Data Structures",
          link: "https://youtu.be/MLqHDsBOC4c",
        },
        {
          name: "Operating Systems",
          link: "https://youtu.be/yK1uBHPdp30",
        },
        {
          name: "Networking",
          link: "https://www.youtube.com/watch?v=IPvYjXCsTg8",
        },
        { name: "AI/ML", link: "https://www.youtube.com/watch?v=GwIo3gDZCVQ" },
        {
          name: "Cloud Computing",
          link: "https://www.youtube.com/watch?v=2LaQDqJH4Rw",
        },
        {
          name: "Cybersecurity",
          link: "https://www.youtube.com/watch?v=nzZkKoREEGo",
        },
        {
          name: "Blockchain",
          link: "https://www.youtube.com/watch?v=gyMwXuJrbJQ",
        },
      ],
      icon: "fa-laptop-code",
    },
    petroleum: {
      title: "Petroleum Engineering",
      courses: [
        {
          name: "Reservoir Engineering",
          link: "https://www.youtube.com/watch?v=8caEIwT1QY0",
        },
        {
          name: "Drilling Technology",
          link: "https://www.youtube.com/watch?v=LwGvj9oogEk",
        },
        {
          name: "Enhanced Oil Recovery",
          link: "https://www.youtube.com/watch?v=0cPF_fYc_0s",
        },
        {
          name: "Sustainable Energy Solutions",
          link: "https://www.youtube.com/watch?v=RnvCbquYeIM",
        },
      ],
      icon: "fa-oil-well",
    },
    textile: {
      title: "Textile Engineering",
      courses: [
        {
          name: "Fabric Manufacturing",
          link: "https://www.youtube.com/watch?v=1tQ8MYf-Opw",
        },
        {
          name: "Textile Chemistry",
          link: "https://www.youtube.com/watch?v=Rp_3QY5ereQ",
        },
        {
          name: "Garment Production",
          link: "https://www.youtube.com/watch?v=s2ThIRw_Yk8",
        },
        {
          name: "Smart Textiles",
          link: "https://www.youtube.com/watch?v=qCxkjhXxqhI",
        },
        {
          name: "Sustainable Practices",
          link: "https://www.youtube.com/watch?v=AdX8K37ElTY",
        },
      ],
      icon: "fa-shirt",
    },
    management: {
      title: "Management",
      courses: [
        {
          name: "Marketing",
          link: "https://www.youtube.com/watch?v=UHS-YsSMXwY",
        },
        {
          name: "Finance",
          link: "https://www.youtube.com/watch?v=WEDIj9JBTC8",
        },
        { name: "HR", link: "https://www.youtube.com/watch?v=jMu6MmB5Yqk" },
        {
          name: "Operations",
          link: "https://www.youtube.com/watch?v=xpx6VrLMc_k",
        },
        {
          name: "Strategic Leadership",
          link: "https://www.youtube.com/watch?v=k0Oc7i5HwEk",
        },
        {
          name: "Business Analytics",
          link: "https://www.youtube.com/watch?v=r6cO_q-h_7I",
        },
        {
          name: "Global Business",
          link: "https://www.youtube.com/watch?v=HlbRwH3n0Js",
        },
      ],
      icon: "fa-briefcase",
    },
    advanced: {
      title: "Advanced Courses",
      courses: [
        {
          name: "Renewable Energy",
          link: "https://www.youtube.com/watch?v=1kUE0BZtTRc",
        },
        {
          name: "Industry 4.0",
          link: "https://www.youtube.com/watch?v=AIqqwhRhJ0E",
        },
        {
          name: "Data Science",
          link: "https://www.youtube.com/watch?v=ua-CiDNNj30",
        },
        {
          name: "Project Management",
          link: "https://www.youtube.com/watch?v=TiZxPvX0_WU",
        },
      ],
      icon: "fa-graduation-cap",
    },
  };

  return (
    <div className="min-h-screen bg-gradient-to-b from-[#1a237e] to-[#303f9f] p-6">
      <div className="max-w-7xl mx-auto">
        <h1 className="text-5xl font-bold text-white mb-8 text-center font-roboto tracking-tight">
          <span className="inline-block animate-bounce">🎓</span> Learn
          Engineering & Management
        </h1>
        <div className="mb-8 max-w-md mx-auto">
          <div className="relative">
            <input
              type="text"
              placeholder="Type to find your course..."
              className="w-full px-4 py-3 rounded-lg bg-white/90 backdrop-blur-sm focus:outline-none focus:ring-2 focus:ring-[#1a237e] text-gray-800 placeholder-gray-500 text-lg"
              value={searchTerm}
              onChange={(e) => setSearchTerm(e.target.value)}
            />
            <i className="fas fa-search absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-500"></i>
          </div>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
          {Object.entries(fields)
            .filter(
              ([_, field]) =>
                field.title.toLowerCase().includes(searchTerm.toLowerCase()) ||
                field.courses.some((course) =>
                  course.name.toLowerCase().includes(searchTerm.toLowerCase())
                )
            )
            .map(([key, field]) => (
              <div
                key={key}
                onClick={() =>
                  setSelectedField(selectedField === key ? null : key)
                }
                className={`bg-white/95 backdrop-blur-sm rounded-xl p-6 shadow-lg hover:shadow-2xl transition-all duration-300 cursor-pointer ${
                  selectedField === key
                    ? "ring-4 ring-[#1a237e]/50 transform scale-[1.02]"
                    : "hover:scale-[1.02]"
                }`}
              >
                <div className="flex items-center mb-4">
                  <div className="w-14 h-14 rounded-full bg-[#1a237e]/10 flex items-center justify-center">
                    <i
                      className={`fas ${field.icon} text-[#1a237e] text-2xl`}
                    ></i>
                  </div>
                  <h2 className="text-2xl font-semibold font-roboto ml-4 text-gray-800">
                    {field.title}
                  </h2>
                </div>

                {selectedField === key && (
                  <div className="mt-6">
                    <ul className="space-y-4">
                      {field.courses.map((course, index) => (
                        <li
                          key={index}
                          onMouseEnter={() => setHoveredCourse(index)}
                          onMouseLeave={() => setHoveredCourse(null)}
                          className="flex items-center justify-between p-3 rounded-lg hover:bg-[#1a237e]/5 transition-all duration-200"
                        >
                          <div className="flex items-center flex-1">
                            <i className="fas fa-play-circle text-[#1a237e] mr-3 text-xl"></i>
                            <span className="text-gray-700 font-medium text-lg">
                              {course.name}
                            </span>
                          </div>
                          <a
                            href={course.link}
                            target="_blank"
                            rel="noopener noreferrer"
                            onClick={(e) => e.stopPropagation()}
                            className={`p-2 rounded-full transition-all duration-200 ${
                              hoveredCourse === index
                                ? "bg-red-500 text-white"
                                : "hover:bg-[#1a237e]/10"
                            }`}
                          >
                            <i className="fab fa-youtube text-xl"></i>
                          </a>
                        </li>
                      ))}
                    </ul>
                  </div>
                )}
              </div>
            ))}
        </div>
      </div>
    </div>
  );
}

export default MainComponent;
