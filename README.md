import React, { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { motion } from "framer-motion";

const chapters = [
  "Chapter 1: Hello! Let's Begin!",
  "Chapter 2: My Family",
  "Chapter 3: Colors and Numbers",
  "Chapter 4: School and Classroom",
  "Chapter 5: Grammar Fun",
  "Chapter 6: Talking About Time",
  "Chapter 7: My Daily Routine",
  "Chapter 8: Reading Time!",
  "Chapter 9: Simple Math in English",
  "Chapter 10: Final Challenge!"
];

const chapterImages = {
  "Chapter 1: Hello! Let's Begin!": "https://cdn.pixabay.com/photo/2015/08/13/14/44/kids-887389_1280.jpg",
  "Chapter 2: My Family": "https://cdn.pixabay.com/photo/2017/08/06/15/13/family-2590000_1280.jpg",
  "Chapter 3: Colors and Numbers": "https://cdn.pixabay.com/photo/2016/03/31/19/14/numbers-1293964_1280.png",
  "Chapter 4: School and Classroom": "https://cdn.pixabay.com/photo/2016/11/22/19/14/classroom-1853740_1280.jpg",
  "Chapter 5: Grammar Fun": "https://cdn.pixabay.com/photo/2016/02/09/16/47/school-1186875_1280.jpg",
  "Chapter 6: Talking About Time": "https://cdn.pixabay.com/photo/2016/11/29/10/07/alarm-clock-1867158_1280.jpg",
  "Chapter 7: My Daily Routine": "https://cdn.pixabay.com/photo/2018/05/11/09/55/clock-3387288_1280.jpg",
  "Chapter 8: Reading Time!": "https://cdn.pixabay.com/photo/2016/09/04/18/56/book-1644856_1280.jpg",
  "Chapter 9: Simple Math in English": "https://cdn.pixabay.com/photo/2016/04/15/11/46/abacus-1331110_1280.jpg",
  "Chapter 10: Final Challenge!": "https://cdn.pixabay.com/photo/2017/06/10/06/07/finish-2389230_1280.jpg"
};

export default function EnglishIsFunWorkbook() {
  const [activeChapter, setActiveChapter] = useState(null);

  const renderChapterContent = (chapter) => {
    return (
      <div className="text-[Times New Roman] space-y-4">
        <h2 className="text-2xl font-bold text-black">📘 {chapter}</h2>
        <p><span className="text-blue-600 font-semibold">Welcome</span> to {chapter}! 🎉 Let's learn together with Teacher Sam 🤖!</p>
        <p>Here's where we will explore exciting words and ideas. Don't worry — Teacher Sam is here to guide you with jokes, smiles, and learning fun!</p>
        <img src={chapterImages[chapter]} className="w-full rounded-lg" alt="Chapter Illustration" />
        <p className="italic text-green-600">🏆 You're doing great! Keep going and don’t forget to smile like Sam 😄</p>
      </div>
    );
  };

  return (
    <div className="grid gap-6 p-6 bg-sky-100 text-[Times New Roman]">
      {/* Cover Page */}
      <motion.div
        initial={{ opacity: 0, y: -30 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.6 }}
        className="text-center"
      >
        <h1 className="text-4xl font-bold mb-2">🌟 Welcome to the "English is Fun!" Workbook 🌟</h1>
        <p className="text-lg italic">Used by Teacher Sam 🤖</p>
        <img
          src="/mnt/data/A_2D_digital_illustration_depicts_Sam,_a_friendly_.png"
          alt="Teacher Sam"
          className="mx-auto w-40 h-auto mt-4"
        />
      </motion.div>

      {/* Introduction Section */}
      <Card>
        <CardContent className="p-6 space-y-4">
          <div>
            <h2 className="text-2xl font-bold text-black">🎯 Our Mission</h2>
            <p>To make learning English fun, easy, and meaningful for every child — no matter where they come from or what level they start at.</p>
          </div>
          <div>
            <h2 className="text-2xl font-bold text-black">👀 Our Vision</h2>
            <p>To build a generation of confident, creative, and curious English speakers who are ready to express themselves and explore the world!</p>
          </div>
          <div>
            <h2 className="text-2xl font-bold text-black">💖 Our Core Values</h2>
            <ul className="list-disc pl-6 space-y-1">
              <li><span className="text-blue-600 font-semibold">Respect</span>: We treat everyone kindly and listen to each other.</li>
              <li><span className="text-green-600 font-semibold">Creativity</span>: We learn through games, stories, songs, and colors!</li>
              <li><span className="text-blue-600 font-semibold">Discipline</span>: We come on time, participate, and keep our work neat.</li>
              <li><span className="text-green-600 font-semibold">Joy</span>: We believe that smiling and having fun helps us learn better.</li>
              <li><span className="text-blue-600 font-semibold">Teamwork</span>: We help each other and grow together.</li>
            </ul>
          </div>
          <div>
            <h2 className="text-2xl font-bold text-black">🤖 Why Teacher Sam?</h2>
            <p>Teacher Sam is not just any teacher. He's your friendly guide through fun, stories, jokes, and joyful learning! He will sometimes say funny things like: <em>“Oops! I dropped my grammar book! Just kidding — I never drop knowledge!”</em> 😂</p>
          </div>
        </CardContent>
      </Card>

      {/* Navigation Buttons */}
      <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-4">
        {chapters.map((chapter) => (
          <button
            key={chapter}
            onClick={() => setActiveChapter(chapter)}
            className="bg-white text-sky-700 font-semibold py-2 px-4 rounded-xl shadow hover:bg-sky-50"
          >
            {chapter}
          </button>
        ))}
      </div>

      {/* Chapter Content */}
      {activeChapter && (
        <Card>
          <CardContent className="p-6">
            {renderChapterContent(activeChapter)}
          </CardContent>
        </Card>
      )}
    </div>
  );
}
