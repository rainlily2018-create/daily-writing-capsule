<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Daily Writing Capsule - Year 4</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap" rel="stylesheet">

    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .capsule-container {
            max-width: 800px;
            margin: 2rem auto;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            border-radius: 1rem;
            overflow: hidden;
        }
        .nav-button {
            transition: all 0.3s ease;
            border-bottom: 4px solid transparent;
        }
        .nav-button.active {
            border-bottom-color: #0d9488; /* teal-600 */
            color: #0d9488;
            font-weight: 600;
        }
        .content-card {
            min-height: 400px;
        }
        .interactive-input {
            border: none;
            border-bottom: 2px dotted #94a3b8; /* slate-400 */
            outline: none;
            padding: 0.25rem 0.5rem;
            background-color: transparent;
            transition: border-color 0.2s ease-in-out;
            min-width: 150px;
        }
        .interactive-input:focus {
            border-bottom-style: solid;
            border-bottom-color: #14b8a6; /* teal-500 */
        }
        .interactive-textarea {
            transition: all 0.2s ease;
            border-radius: 0.5rem;
            border: 1px solid #cbd5e1; /* slate-300 */
        }
        .interactive-textarea:focus {
            box-shadow: 0 0 0 2px #a7f3d0; /* emerald-200 */
            border-color: #14b8a6; /* teal-500 */
            outline: none;
        }
         /* Certificate Styles */
        .certificate {
            border: 10px solid #0d9488;
            border-image: linear-gradient(to right, #0d9488, #f59e0b) 1;
            font-family: 'Playfair Display', serif;
        }
        .modal {
            transition: opacity 0.3s ease;
        }
        .signature-font {
            font-family: 'Dancing Script', cursive;
        }
    </style>
</head>
<body class="bg-slate-100">

    <div class="capsule-container bg-white">
        <!-- Header -->
        <header class="bg-teal-600 p-6">
            <div class="flex justify-center mb-4">
                <a href="https://ibb.co/pjTDRmgh"><img src="https://i.ibb.co/gZ81PnG4/LOGO-PPD-BALING-WHITE.png" alt="LOGO-PPD-BALING-WHITE" border="0" class="h-20"></a>
            </div>
            <h1 class="text-3xl font-bold text-white text-center tracking-wide">DAILY WRITING CAPSULE</h1>
            <p class="text-center text-teal-100 mt-1">Year 4 - Interactive Activities with AI Assessment</p>
        </header>

        <!-- Week Navigation -->
        <nav class="bg-white border-b border-slate-200">
            <ul class="flex flex-wrap justify-center p-2">
                <li><button data-week="1" class="nav-button active text-slate-600 py-3 px-4 text-sm md:text-base">Week 1</button></li>
                <li><button data-week="2" class="nav-button text-slate-600 py-3 px-4 text-sm md:text-base">Week 2</button></li>
                <li><button data-week="3" class="nav-button text-slate-600 py-3 px-4 text-sm md:text-base">Week 3</button></li>
                <li><button data-week="4" class="nav-button text-slate-600 py-3 px-4 text-sm md:text-base">Week 4</button></li>
                <li><button data-week="5" class="nav-button text-slate-600 py-3 px-4 text-sm md:text-base">Week 5</button></li>
                <li><button data-week="6" class="nav-button text-slate-600 py-3 px-4 text-sm md:text-base">Week 6</button></li>
                <li><button data-week="7" class="nav-button text-slate-600 py-3 px-4 text-sm md:text-base">Week 7</button></li>
                <li><button data-week="8" class="nav-button text-slate-600 py-3 px-4 text-sm md:text-base">Week 8</button></li>
            </ul>
        </nav>

        <!-- Content Area -->
        <main class="p-6 md:p-8">
             <div class="mb-6">
                <label for="studentName" class="block text-lg font-semibold text-slate-700 mb-2">Student's Name:</label>
                <input type="text" id="studentName" placeholder="Enter your full name here" class="w-full md:w-2/3 p-2 border border-slate-300 rounded-md focus:ring-2 focus:ring-teal-300 focus:border-teal-500 outline-none transition">
                <p id="nameError" class="text-sm text-red-600 mt-1 h-4"></p>
                <p class="text-sm text-slate-500 -mt-1">Please enter your name before checking your work or getting a certificate.</p>
             </div>

            <!-- Week 1 Content -->
            <div id="week-1" class="week-content content-card">
                <h2 class="text-2xl font-bold text-slate-800">Week 1: Myself</h2>
                <h3 class="text-lg font-semibold text-teal-700 mt-2">Sentence Starters</h3>
                <p class="text-slate-600 mb-6">Complete the sentences.</p>
                <div class="space-y-4 text-slate-700">
                    <p data-prompt="My name is..."><span class="font-semibold w-28 inline-block">Sunday:</span> My name is <input type="text" class="interactive-input w-1/2">.</p>
                    <p data-prompt="I am... years old."><span class="font-semibold w-28 inline-block">Monday:</span> I am <input type="text" class="interactive-input w-1/4"> years old.</p>
                    <p data-prompt="I live in..."><span class="font-semibold w-28 inline-block">Tuesday:</span> I live in <input type="text" class="interactive-input w-1/2">.</p>
                    <p data-prompt="My favourite colour is..."><span class="font-semibold w-28 inline-block">Wednesday:</span> My favourite colour is <input type="text" class="interactive-input w-1/3">.</p>
                    <p data-prompt="My best friend is..."><span class="font-semibold w-28 inline-block">Thursday:</span> My best friend is <input type="text" class="interactive-input w-1/2">.</p>
                </div>
                <div class="mt-8">
                    <button onclick="checkWriting(1)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors">Check My Writing & Get Band</button>
                    <div id="result-1" class="result-area mt-4 text-left"></div>
                </div>
            </div>

            <!-- Week 2 Content -->
            <div id="week-2" class="week-content content-card hidden">
                <h2 class="text-2xl font-bold text-slate-800">Week 2: My Family</h2>
                 <h3 class="text-lg font-semibold text-teal-700 mt-2">Sentence Starters</h3>
                <p class="text-slate-600 mb-6">Complete the sentences.</p>
                 <div class="space-y-4 text-slate-700">
                    <p data-prompt="My father’s name is..."><span class="font-semibold w-28 inline-block">Sunday:</span> My father’s name is <input type="text" class="interactive-input w-1/2">.</p>
                    <p data-prompt="My mother is... years old."><span class="font-semibold w-28 inline-block">Monday:</span> My mother is <input type="text" class="interactive-input w-1/4"> years old.</p>
                    <p data-prompt="I have ... brothers."><span class="font-semibold w-28 inline-block">Tuesday:</span> I have <input type="text" class="interactive-input w-1/4"> brothers.</p>
                    <p data-prompt="I have ... sisters."><span class="font-semibold w-28 inline-block">Wednesday:</span> I have <input type="text" class="interactive-input w-1/4"> sisters.</p>
                    <p data-prompt="I love my family because..."><span class="font-semibold w-28 inline-block">Thursday:</span> I love my family because <input type="text" class="interactive-input w-1/2">.</p>
                </div>
                 <div class="mt-8">
                    <button onclick="checkWriting(2)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors">Check My Writing & Get Band</button>
                    <div id="result-2" class="result-area mt-4 text-left"></div>
                </div>
            </div>

            <!-- Week 3 Content -->
            <div id="week-3" class="week-content content-card hidden">
                <h2 class="text-2xl font-bold text-slate-800">Week 3: My School</h2>
                <h3 class="text-lg font-semibold text-teal-700 mt-2">Word Bank</h3>
                <p class="text-slate-600 mb-4">Write 2–3 sentences each day using 2 words from the bank.</p>
                 <div class="p-4 bg-green-50 border border-green-200 rounded-lg text-green-800 mb-4">
                    <span class="font-semibold">Word Bank:</span> teacher, friends, read, play, library
                </div>
                <div class="mt-6 space-y-6 text-slate-700">
                    <div>
                        <p class="font-semibold mb-2">Sunday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Sunday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Monday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Monday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Tuesday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Tuesday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Wednesday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Wednesday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Thursday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Thursday..."></textarea>
                    </div>
                </div>
                 <div class="mt-8">
                    <button onclick="checkWriting(3)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors">Check My Writing & Get Band</button>
                    <div id="result-3" class="result-area mt-4 text-left"></div>
                </div>
            </div>

            <!-- Week 4 Content -->
            <div id="week-4" class="week-content content-card hidden">
                <h2 class="text-2xl font-bold text-slate-800">Week 4: Food & Drinks</h2>
                <h3 class="text-lg font-semibold text-teal-700 mt-2">Word Bank</h3>
                <p class="text-slate-600 mb-4">Write 2–3 sentences each day about what you eat or drink.</p>
                <div class="p-4 bg-green-50 border border-green-200 rounded-lg text-green-800 mb-4">
                    <span class="font-semibold">Word Bank:</span> rice, chicken, water, noodles, breakfast
                </div>
                <div class="mt-6 space-y-6 text-slate-700">
                    <div>
                        <p class="font-semibold mb-2">Sunday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Sunday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Monday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Monday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Tuesday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Tuesday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Wednesday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Wednesday..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Thursday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Thursday..."></textarea>
                    </div>
                </div>
                 <div class="mt-8">
                    <button onclick="checkWriting(4)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors">Check My Writing & Get Band</button>
                    <div id="result-4" class="result-area mt-4 text-left"></div>
                </div>
            </div>

            <!-- Week 5 Content -->
            <div id="week-5" class="week-content content-card hidden">
                <h2 class="text-2xl font-bold text-slate-800">Week 5: Daily Routine</h2>
                <h3 class="text-lg font-semibold text-teal-700 mt-2">Word Bank</h3>
                <p class="text-slate-600 mb-4">Write 3 sentences each day about your daily routine.</p>
                <div class="p-4 bg-green-50 border border-green-200 rounded-lg text-green-800 mb-4">
                    <span class="font-semibold">Word Bank:</span> wake up, brush, school, lunch, sleep
                </div>
                <div class="mt-6 space-y-6 text-slate-700">
                    <div>
                        <p class="font-semibold mb-2">Sunday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Sunday..."></textarea>
                    </div>
                     <div>
                        <p class="font-semibold mb-2">Monday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Monday..."></textarea>
                    </div>
                     <div>
                        <p class="font-semibold mb-2">Tuesday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Tuesday..."></textarea>
                    </div>
                     <div>
                        <p class="font-semibold mb-2">Wednesday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Wednesday..."></textarea>
                    </div>
                     <div>
                        <p class="font-semibold mb-2">Thursday:</p>
                        <textarea class="interactive-textarea w-full p-2" rows="2" placeholder="Write your sentences for Thursday..."></textarea>
                    </div>
                </div>
                 <div class="mt-8">
                    <button onclick="checkWriting(5)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors">Check My Writing & Get Band</button>
                    <div id="result-5" class="result-area mt-4 text-left"></div>
                </div>
            </div>

            <!-- Week 6 Content -->
            <div id="week-6" class="week-content content-card hidden">
                <h2 class="text-2xl font-bold text-slate-800">Week 6: My Favourite</h2>
                <h3 class="text-lg font-semibold text-teal-700 mt-2">Open Prompt</h3>
                <p class="text-slate-600 mb-4">Write 3-4 sentences about the topic for each day.</p>
                <div class="space-y-6 text-slate-700">
                    <div>
                        <p class="font-semibold mb-2">Sunday: Write about your favourite game.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Monday: Write about your favourite subject.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Tuesday: Write about your favourite toy.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Wednesday: Write about your favourite day of the week.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Thursday: Write about your favourite fruit.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                </div>
                 <div class="mt-8">
                    <button onclick="checkWriting(6)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors">Check My Writing & Get Band</button>
                    <div id="result-6" class="result-area mt-4 text-left"></div>
                </div>
            </div>

            <!-- Week 7 Content -->
            <div id="week-7" class="week-content content-card hidden">
                <h2 class="text-2xl font-bold text-slate-800">Week 7: My Weekend</h2>
                <h3 class="text-lg font-semibold text-teal-700 mt-2">Open Prompt</h3>
                <p class="text-slate-600 mb-4">Write 4 sentences about the topic for each day.</p>
                <div class="space-y-6 text-slate-700">
                    <div>
                        <p class="font-semibold mb-2">Sunday: Write about what you did last Saturday.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Monday: Write about what you ate last Sunday.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Tuesday: Write about who you met during the weekend.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Wednesday: Write about where you went.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Thursday: Write about how you felt.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                </div>
                <div class="mt-8">
                    <button onclick="checkWriting(7)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors">Check My Writing & Get Band</button>
                    <div id="result-7" class="result-area mt-4 text-left"></div>
                </div>
            </div>
            
            <!-- Week 8 Content -->
            <div id="week-8" class="week-content content-card hidden">
                <h2 class="text-2xl font-bold text-slate-800">Week 8: Imagination Week</h2>
                <h3 class="text-lg font-semibold text-teal-700 mt-2">Creative Writing</h3>
                <p class="text-slate-600 mb-4">Write 4 sentences about the topic for each day.</p>
                <div class="space-y-6 text-slate-700">
                    <div>
                        <p class="font-semibold mb-2">Sunday: Imagine you have a pet dinosaur.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Monday: Imagine you are a superhero.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Tuesday: Imagine you are invisible.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Wednesday: Imagine you can fly.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                    <div>
                        <p class="font-semibold mb-2">Thursday: Imagine you are a teacher.</p>
                        <textarea class="interactive-textarea w-full p-2" rows="3" placeholder="Write your answer here..."></textarea>
                    </div>
                </div>
                <div class="mt-8">
                    <button onclick="checkWriting(8)" class="check-button w-full bg-teal-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-teal-700 transition-colors mb-4">Check My Writing & Get Band</button>
                     <div id="result-8" class="result-area mt-4 text-left"></div>

                    <div class="mt-8 text-center border-t pt-8">
                        <button id="finalCertButton" onclick="showFinalCertificate()" class="bg-amber-500 text-white font-bold py-2 px-6 rounded-lg hover:bg-amber-600 transition-colors disabled:bg-slate-400 disabled:cursor-not-allowed" disabled>
                            Get Final Certificate
                        </button>
                        <p id="certMessage" class="text-sm text-slate-500 mt-2">
                            Complete all activities from Week 1 to Week 8 to unlock your certificate.
                        </p>
                    </div>
                </div>
            </div>
        </main>

        <!-- Footer -->
        <footer class="bg-slate-800 text-slate-300 p-6 text-sm">
             <div class="flex flex-col md:flex-row items-center justify-between">
                <div class="mb-4 md:mb-0 bg-white rounded-full p-1">
                    <a href="https://ibb.co/fd07m8sR">
                        <img src="https://i.ibb.co/Ldpf4Q3w/BANGKITBALINGBANGKIT-removebg-preview.png" alt="BANGKITBALINGBANGKIT-removebg-preview" class="h-10 w-10">
                    </a>
                </div>
                <div class="text-center md:text-right">
                    <p class="font-bold text-white mb-1">Contact Us:</p>
                    <p>Dr. Chin Da Bun Tiang | SISC+ (Language)</p>
                    <p>Baling District Education Office</p>
                    <div class="flex items-center justify-center md:justify-end mt-1">
                         <svg class="w-4 h-4 mr-2" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"></path><path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"></path></svg>
                        <a href="mailto:chinda@moe.gov.my" class="hover:text-teal-400 transition-colors">chinda@moe.gov.my</a>
                    </div>
                </div>
            </div>
        </footer>
    </div>

    <!-- Certificate Modal -->
    <div id="certificateModal" class="modal fixed inset-0 bg-black bg-opacity-75 flex items-center justify-center p-4 opacity-0 pointer-events-none z-50">
        <div class="bg-white p-6 md:p-8 rounded-lg max-w-3xl w-full relative">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-slate-500 hover:text-slate-800 p-1 rounded-full hover:bg-slate-200 transition">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
            </button>
            <div id="certificateContent" class="certificate p-8 text-center bg-slate-50">
                <img src="https://i.ibb.co/spxfZ7kJ/LOGO-PPD-BALING.png" alt="LOGO PPD BALING" class="h-24 mx-auto mb-4">
                <h2 class="text-4xl md:text-5xl text-amber-600">Certificate of Achievement</h2>
                <p class="text-lg text-slate-600 mt-4">This certificate is proudly presented to</p>
                <p id="certStudentName" class="text-3xl md:text-4xl font-bold text-teal-800 my-6"></p>
                <p class="text-lg text-slate-600">for successfully completing the</p>
                <p id="certWeekTopic" class="text-2xl font-semibold text-slate-800 my-2"></p>
                <div class="flex justify-between items-center mt-12 text-sm text-slate-700" style="font-family: 'Inter', sans-serif;">
                    <div>
                        <p id="certDate" class="border-t-2 border-slate-400 px-4 pt-1"></p>
                        <p class="font-semibold">Date</p>
                    </div>
                    <div class="text-center">
                        <p class="signature-font text-4xl text-slate-700">Chinda</p>
                        <p class="border-t-2 border-slate-400 mt-2 px-4 pt-1 font-semibold">Dr. Chin Da Bun Tiang</p>
                        <p class="font-semibold">SISC+ (Language)</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        const navButtons = document.querySelectorAll('.nav-button');
        const weekContents = document.querySelectorAll('.week-content');
        const studentNameInput = document.getElementById('studentName');
        const nameError = document.getElementById('nameError');
        const allInputs = document.querySelectorAll('.interactive-input, .interactive-textarea');
        const certificateModal = document.getElementById('certificateModal');
        const finalCertButton = document.getElementById('finalCertButton');
        const certMessage = document.getElementById('certMessage');

        // --- PROGRESS SAVING & COMPLETION CHECK ---
        function checkCompletion() {
            let isComplete = true;
            allInputs.forEach(input => {
                if (input.value.trim() === '') {
                    isComplete = false;
                }
            });

            if (isComplete) {
                finalCertButton.disabled = false;
                certMessage.textContent = 'Congratulations! You have completed all activities.';
                certMessage.classList.remove('text-slate-500');
                certMessage.classList.add('text-green-600', 'font-semibold');
            } else {
                finalCertButton.disabled = true;
                certMessage.textContent = 'Complete all activities from Week 1 to Week 8 to unlock your certificate.';
                certMessage.classList.add('text-slate-500');
                certMessage.classList.remove('text-green-600', 'font-semibold');
            }
        }
        
        function saveProgress() {
            const dataToSave = {};
            allInputs.forEach((input, index) => {
                const id = `input_${input.closest('.week-content').id}_${index}`;
                dataToSave[id] = input.value;
            });
            localStorage.setItem('writingCapsuleProgress', JSON.stringify(dataToSave));
            localStorage.setItem('writingCapsuleName', studentNameInput.value);
            checkCompletion();
        }

        function loadProgress() {
            const savedName = localStorage.getItem('writingCapsuleName');
            if (savedName) studentNameInput.value = savedName;
            const savedProgress = JSON.parse(localStorage.getItem('writingCapsuleProgress'));
            if (savedProgress) {
                allInputs.forEach((input, index) => {
                    const id = `input_${input.closest('.week-content').id}_${index}`;
                    if (savedProgress[id]) {
                        input.value = savedProgress[id];
                    }
                });
            }
            checkCompletion();
        }

        studentNameInput.addEventListener('input', () => {
             nameError.textContent = "";
             studentNameInput.classList.remove('border-red-500', 'ring-red-500');
             saveProgress();
        });
        allInputs.forEach(input => input.addEventListener('input', saveProgress));
        window.addEventListener('load', loadProgress);

        // --- NAVIGATION ---
        navButtons.forEach(button => {
            button.addEventListener('click', () => {
                const week = button.dataset.week;
                navButtons.forEach(btn => btn.classList.remove('active'));
                button.classList.add('active');
                weekContents.forEach(content => content.classList.toggle('hidden', content.id !== `week-${week}`));
            });
        });
        
        // --- AI CHECKING ---
        async function checkWriting(weekNumber) {
            const studentName = studentNameInput.value.trim();
            if (!studentName) {
                nameError.textContent = "Please enter your name first!";
                studentNameInput.classList.add('border-red-500', 'ring-red-500');
                studentNameInput.focus();
                return;
            } else {
                nameError.textContent = "";
                studentNameInput.classList.remove('border-red-500', 'ring-red-500');
            }

            const weekContainer = document.getElementById(`week-${weekNumber}`);
            const resultArea = document.getElementById(`result-${weekNumber}`);
            const checkButton = weekContainer.querySelector('.check-button');

            resultArea.innerHTML = `<div class="flex items-center justify-center p-4 bg-blue-50 border border-blue-200 rounded-lg"><svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-blue-500" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"><circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle><path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path></svg><span>Your AI Coach is assessing the writing...</span></div>`;
            checkButton.disabled = true;

            let studentWriting = "";
            const inputs = weekContainer.querySelectorAll('input[type="text"], textarea');
            inputs.forEach(input => {
                const parentEl = input.closest('[data-prompt]');
                const promptText = parentEl ? parentEl.dataset.prompt : (input.previousElementSibling?.textContent || `Response for an item`);
                studentWriting += `Prompt: "${promptText}"\nStudent's Answer: "${input.value}"\n\n`;
            });
            
            const weekTopic = weekContainer.querySelector('h2').textContent;

            const systemPrompt = `You are a friendly and encouraging primary school teacher in Malaysia, evaluating a Year 4 student's writing. Your task is to provide a performance band from 1 to 6.
            Your response MUST be in JSON format.
            The rubric for the bands is:
            - Band 1 (Needs Improvement): Many errors in grammar/spelling, answers are off-topic or incomplete.
            - Band 2 (Fair): Some errors, answers are very basic but on-topic.
            - Band 3 (Satisfactory): Basic sentences are mostly correct, uses simple vocabulary.
            - Band 4 (Good): Good sentence structure, some vocabulary variation, mostly error-free.
            - Band 5 (Very Good): Confident writing, varied sentences, good vocabulary, very few errors.
            - Band 6 (Excellent): Creative, well-structured, wide vocabulary, grammatically flawless, exceeds expectations.

            Analyze the student's writing based on the prompts. Provide the band number and a short, simple justification for the band.`;

            const userQuery = `Please evaluate the following writing for ${weekTopic} and provide a performance band:\n\n${studentWriting}`;
            
            const apiKey = ""; 
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-05-20:generateContent?key=${apiKey}`;

            const payload = {
                contents: [{ parts: [{ text: userQuery }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] },
                generationConfig: {
                    responseMimeType: "application/json",
                    responseSchema: {
                        type: "OBJECT",
                        properties: {
                            "band": { "type": "NUMBER" },
                            "justification": { "type": "STRING" }
                        },
                        required: ["band", "justification"]
                    }
                }
            };

            try {
                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                    throw new Error(`API request failed with status ${response.status}`);
                }
                
                const result = await response.json();
                
                if (result.candidates && result.candidates[0].content) {
                    const parsedJson = JSON.parse(result.candidates[0].content.parts[0].text);
                    displayResults(resultArea, parsedJson);
                } else {
                    if (result.promptFeedback && result.promptFeedback.blockReason) {
                         throw new Error(`Request blocked for reason: ${result.promptFeedback.blockReason}`);
                    }
                    throw new Error("Invalid response structure from API.");
                }

            } catch (error) {
                console.error("AI Coach Error:", error);
                let errorMessage = "Oops! Something went wrong communicating with the AI Coach. Please try again in a moment.";
                if (error.message.includes("API request failed")) {
                    errorMessage = `There was a network problem (Error: ${error.message}). Please check your connection and try again.`;
                } else if (error.message.includes("blocked")) {
                    errorMessage = "The content could not be checked due to safety filters. Please revise your writing and try again.";
                } else if (error.message.includes("Invalid response structure")) {
                     errorMessage = "The AI Coach provided an empty or invalid response. Please try again.";
                }
                resultArea.innerHTML = `<div class="p-4 bg-red-50 border border-red-200 rounded-lg text-red-800">${errorMessage}</div>`;
            } finally {
                checkButton.disabled = false;
            }
        }

        function displayResults(resultArea, data) {
            resultArea.innerHTML = `
                <div class="p-4 bg-emerald-50 border border-emerald-200 rounded-lg space-y-2">
                    <h4 class="font-bold text-lg text-emerald-800">Assessment Result:</h4>
                    <div class="flex items-center gap-4">
                        <p class="text-5xl font-bold text-emerald-600">${data.band}</p>
                        <div>
                            <p class="font-semibold text-emerald-800">Performance Band</p>
                            <p class="text-sm text-emerald-700">${data.justification}</p>
                        </div>
                    </div>
                </div>
            `;
        }
        
        // --- CERTIFICATE MODAL ---
        function showFinalCertificate() {
            const studentName = studentNameInput.value.trim();
            if (!studentName) {
                nameError.textContent = "Please enter your name first!";
                studentNameInput.classList.add('border-red-500', 'ring-red-500');
                studentNameInput.focus();
                return;
            }
            
            document.getElementById('certStudentName').textContent = studentName;
            document.getElementById('certWeekTopic').textContent = "8-Week Daily Writing Capsule";
            document.getElementById('certDate').textContent = new Date().toLocaleDateString('en-GB');
            
            certificateModal.classList.remove('opacity-0', 'pointer-events-none');
        }

        function closeModal() {
            certificateModal.classList.add('opacity-0', 'pointer-events-none');
        }
    </script>
</body>
</html>
