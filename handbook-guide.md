# Handbook Writing Guide

One line per page: what to cover. ✅ = already written, and the line summarizes what's there.

**Page recipe, taken from your written pages:**
1. Open with who invented or discovered it, and why (Beginning, Early Studies, First Computer).
2. Give an everyday illustration (buying food, the light switch, Bert's library, the keyboard and display).
3. Show the binary/logic version: a truth table, an equation, then gates.
4. Close by turning it into a building block for the next page (First Abstraction).

---

### Numbers
- ✅ **Beginning**: two states (yes/no, yin and yang), counting on fingers leads to base 10, the abacus, Pascal's and Leibniz's calculators, and Leibniz's idea of binary.
- ✅ **Binary Number**: what "binary" means, counting 0, 1, 10, 11, base-n to decimal with powers, and decimal to binary by repeated division.
- **Hexadecimal**: base 16 (0–9, A–F) as a shorthand where 1 hex digit = 4 bits. Convert `1111 0101` ↔ `F5` using the same method as Binary Number.
- **Binary Arithmetic**: Leibniz's 1703 paper. Add, subtract, multiply and divide binary by hand, column by column, introducing *carry* and *borrow*.
- **Negative Numbers**: binary has no minus sign. Cover the sign bit, one's complement, then two's complement (1945). Show subtraction becoming addition, as a callback to Pascal's complement trick.
- **Fractions and Floating Point**: binary after the point (0.1 = ½), then scientific notation in binary (sign, exponent, mantissa) as Zuse used in the Z3. Explain why 0.1 + 0.2 ≠ 0.3 exactly.
- **Text as Numbers**: give every letter a number. Morse code, then Baudot, then ASCII (1963, 7 bits), then Unicode/UTF-8 for every language and emoji.
- **Images as Numbers**: an image is a grid of pixels. Each pixel is one number (grayscale) or three (RGB, 0–255), so a photo is just a big table of numbers.
- ✅ **Boolean Algebra**: Boole's true/false as 1/0, AND/OR/NOT with everyday examples and truth tables, the algebra laws, and De Morgan's laws.

### Physics
- ✅ **Electricity**: resin fossilizes into amber, the Greek "elektron", Thales rubbing amber, and everyday static electricity.
- ✅ **Magnet**: lodestones in ancient China, magnetizing iron, and the compass for sailors.
- ✅ **Early Studies**: Gilbert separates magnetism from electricity, then Guericke, Gray (conductors and insulators), Du Fay (two charges), Franklin (+/−), and Galvani vs Volta, which leads to the battery.
- **Electromagnetism**: Ørsted's compass twitches near a wire (1820), Ampère explains the force, and Faraday shows induction (1831). The reveal: electricity and magnetism are one force.
- **Electric Circuit**: Ohm (1827). Voltage, current and resistance with the water-pipe analogy, open vs closed circuits, series vs parallel (this sets up AND/OR).
- **Atom and Electron**: Thomson finds the electron (1897), then the Rutherford and Bohr atom. Current is moving electrons, and Franklin guessed the direction backwards (conventional current).
- **Motion and Force**: Newton (1687). Force, mass, acceleration and torque (turning force), needed later for motors and robots.

### Inventions
- **Electric Motor (1821)**: Faraday's wire spins around a magnet, turning electricity into continuous motion. Davenport builds a practical DC motor (1834).
- **Electromagnetic Switch (1825)**: Sturgeon's electromagnet and Henry's stronger coils. A magnet you switch on and off with current, strong enough to pull a metal arm.
- **Relay (1835)**: Henry and Davy. A small current moves an electromagnet that flips a switch in *another* circuit. It was invented to boost telegraph signals. Cover normally open vs normally closed.
- **Analytical Engine (1837)**: Jacquard loom punched cards, then Babbage's "store" and "mill", then Ada Lovelace's first program (1843). Explains what "programmable" means.
- **Vacuum Tubes (1904)**: Edison effect, Fleming's diode, De Forest's triode (1906). Electrons fly through a vacuum and a grid controls them. A switch with no moving parts.
- **Flip-Flop (1918)**: Eccles and Jordan wire two tubes so each holds the other on or off. The circuit stays in its state: the first electronic one-bit memory.
- ✅ **First Computer (1941)**: Zuse's Z1, Z2 and Z3. 2,600 relays, binary floating point, a punched-tape program and lamp output. The first machine to combine binary math with engineering.

### Combinational Logic
- ✅ **Basic Gates Implementation**: Shannon's 1937 thesis. AND = switches in series, OR = parallel, NOT = a normally closed relay, plus NAND/NOR/XOR/XNOR.
- ✅ **First Abstraction**: what abstraction is (the light switch, texting, the ATM, "shoes"). From now on gates are boxes, not relays.
- **Diagram**: gate symbols (AND, OR, NOT, the inversion bubble, NAND…), drawing wires and junctions, inputs on the left and outputs on the right. Redraw the relay circuits as symbols.
- **Truth Table to Circuit**: turn any truth table into a circuit. Pick the rows where the output is 1, AND each row, then OR them together. Example: a simple alarm.
- **Simplification**: use the Boolean laws and the Karnaugh map (1953) to shrink equations so they need fewer gates. This is where the seven-segment equations come from.
- ✅ **Multiplexer and Demultiplexer**: Bert the librarian. A MUX picks one of many inputs using select bits, and a DEMUX sends one input to one of many outputs. Shows 2-to-1 and 1-to-2 with gates.
- ✅ **Encoder and Decoder**: a 0–9 keyboard becomes a 4-bit code through OR gates (encoder), and the 4-bit code drives a seven-segment display (decoder).
- ✅ **Adders**: half adder (XOR + AND), full adder with carry-in, and the ripple carry adder chaining full adders.
- **Subtractors**: half and full subtractor with *borrow*, then the shortcut where two's complement plus an adder does subtraction.
- **Multiplier**: binary multiplication by hand is just AND, shift and add. Build a 2-bit × 2-bit multiplier from AND gates and adders.
- **Comparator**: is A equal to, greater than, or less than B? XNOR each bit for equality, then compare from the most significant bit. Example: checking a PIN.
- **Arithmetic Logic Unit**: put the adder, subtractor, AND/OR and comparator side by side. A MUX (Bert's hand) picks the operation using an opcode.

### Sequential Logic
- **Sequential Logic Introduction**: combinational logic has no memory, sequential logic remembers by feeding output back into input. Example: a light switch vs a doorbell.
- ✅ **SR Latch**: Set/Reset with cross-coupled NOR or NAND gates, the hold state, the invalid state, and storing a value without continuous input.
- **D Latch**: add an enable input to the SR latch and make R = NOT D to remove the invalid state. It stores D only when enabled.
- **Clock**: gates take time (propagation delay), so a clock ticks to make everything update together. Cover period, frequency (Hz) and rising/falling edges. The Z3 ran at about 5 Hz.
- **D Flip-Flop**: stores D only on the rising clock edge. Build it from two D latches (master–slave).
- **JK & T Flip-Flop**: JK fixes the SR invalid state (J = K = 1 toggles). The T flip-flop toggles every clock and is the base of counters.
- **Registers**: several D flip-flops sharing one clock store a whole number. A shift register moves bits left or right (×2, ÷2).
- **Counters**: chain T flip-flops to count in binary (ripple), then a synchronous counter. Example: counter → decoder → seven-segment display makes a digital clock.
- **Finite State Machine**: states, transitions and a clock. Build a traffic light or vending machine from flip-flops and gates.
- **Divider**: division as repeated subtract-and-shift (binary long division), controlled step by step by an FSM.
- **Building a Calculator**: keyboard encoder → registers → ALU (+ − × ÷) → decoder → seven-segment display, with an FSM running the steps.

### Semiconductor
- **Material**: between conductors and insulators (a Gray callback). Silicon atoms, electrons and holes, and doping to make n-type and p-type material.
- **Basic Devices**: the p-n junction diode (a one-way door), and the transistor at Bell Labs (1947, Bardeen, Brattain, Shockley). A small signal controls a big one, like a relay with no moving parts.
- **Transistor Logic Gates**: the MOSFET as an on/off switch, and nMOS + pMOS = CMOS (1963). Build NOT, NAND and NOR from transistors: the same gates on a new switch.
- **Fabrication**: from sand to a silicon wafer, photolithography (printing patterns with light), doping, layers, cutting into chips, and packaging.

### Modern Computers
- **ENIAC (1945)**: about 17,000 vacuum tubes, decimal, and programmed by rewiring cables. Fast, but huge and hot, and tubes burn out.
- **Stored-Program Computer (1948)**: von Neumann's idea (1945) to keep the program in memory like data. The Manchester Baby runs the first stored program (1948).
- **Transistor Computer (1954)**: TRADIC and TX-0. Transistors replace tubes, making computers smaller, cooler and more reliable with the same logic.
- **Integrated Circuit (1958)**: Kilby and Noyce put many transistors and their wires on one piece of silicon.
- **Moore's Law (1965)**: transistor counts double about every two years, and why that made everything after possible.
- **Microprocessor (1971)**: the Intel 4004, a whole CPU on one chip (about 2,300 transistors vs the Z3's 2,600 relays).
- **Microcontroller (1974)**: the TI TMS1000, with CPU, memory and I/O on one chip, made to embed in calculators, appliances and later robots.
- **Personal Computer (1977)**: the Apple II, Commodore PET and TRS-80 bring computers into homes with a keyboard and screen. Then the IBM PC (1981).
- **Graphics Processing Unit (1999)**: graphics needs the same math on millions of pixels at once. Nvidia's GeForce 256 has many small cores working in parallel, which are later reused for AI.

### Computer Architecture
- **Memory**: RAM is a grid of registers. A decoder picks the address and a MUX reads it out (Bert's library: shelves = addresses).
- **Bus**: shared wires that carry data, addresses and control signals between the CPU, memory and I/O.
- **Instruction Set**: instructions are binary numbers (opcode + operands), such as LOAD, ADD, STORE and JUMP. The CPU's vocabulary.
- **Control Unit**: an FSM that decodes each instruction and tells the ALU, registers and memory what to do on each clock tick.
- **Central Processing Unit**: ALU + registers + control unit + program counter, running the fetch–decode–execute cycle.
- **Input and Output**: how the keyboard, screen and other devices talk to the CPU. I/O ports, polling vs interrupts.
- **Analog and Digital**: the real world is continuous. An ADC turns a voltage into a binary number, and a DAC or PWM turns numbers back into voltage or motion.
- **Building a Simple CPU**: build a tiny 4-bit or 8-bit CPU from the earlier pages and run a short program step by step.
- **Memory Hierarchy**: registers → cache → RAM → storage (disk/SSD). Fast and small vs slow and big, and why caches help.
- **Parallel Processing**: doing many things at once. Multiple cores, SIMD, and why GPUs have thousands of simple cores.

### Software
- **Machine Code**: programs as raw binary (written in hex) loaded into memory. Write a tiny program for the Simple CPU.
- **Assembly Language**: human-readable names for instructions (ADD, MOV), translated by an assembler. The first software abstraction.
- **Programming Languages**: FORTRAN (1957), C (1972), Python (1991). Variables, if, loops and functions: one line replaces many instructions.
- **Compiler**: Grace Hopper's A-0 (1952) and the FORTRAN compiler translate high-level code into machine code. Compiler vs interpreter.
- **Data Structures**: arrays, lists, stacks, queues, trees and hash tables. An array is a row in memory, and a 2D array is a matrix.
- **Algorithms**: step-by-step recipes for search, sort and shortest path, plus Big-O (how time grows with input size).
- **Operating System**: software that manages the hardware: running programs (processes), memory, files on storage, and drivers. Unix (1969).

### Network
- **ARPANET (1969)**: connecting distant computers with packet switching. The first message, "LO", went from UCLA to Stanford.
- **TCP/IP (1974)**: Cerf and Kahn's rules that let any networks talk. IP addresses route packets, and TCP makes sure they arrive in order.
- **World Wide Web (1989)**: Berners-Lee at CERN. Pages (HTML), links, URLs, HTTP and browsers. The web's text later trains LLMs.

### Mathematics
- **Functions**: a machine that takes input and gives output (f(x) = 2x + 1), and graphs. A neural network is one big function.
- **Trigonometry**: angles, and sin and cos on the unit circle. Finding a position from an angle, used for robot arms.
- **Vectors**: a list of numbers drawn as an arrow (direction + length). Adding, scaling, and the dot product as "how similar".
- **Matrices**: a grid of numbers (Cayley, 1858). Matrix × vector and matrix × matrix are many dot products at once.
- **Rotation and Transformation**: matrices that rotate, scale and move points, and chaining coordinate frames.
- **Derivatives**: Newton and Leibniz (Leibniz again). Slope and rate of change: how much the output moves when the input is nudged.
- **Integrals**: the opposite of derivatives, adding up small pieces (area, distance from speed). The "I" in PID.
- **Chain Rule**: the derivative of a function inside a function: multiply the rates. This is what backpropagation uses.
- **Gradient Descent**: Cauchy (1847, the same year as Boole). Walk downhill using the gradient to find the minimum.
- **Probability**: Pascal and Fermat (1654, Pascal again). Chance, events, distributions and conditional probability.
- **Statistics**: mean, variance, standard deviation, the normal distribution, and normalizing data.
- **Exponential and Logarithm**: Napier (1614, a Beginning callback), the number e, growth, and how log turns multiplication into addition.
- **Softmax**: turn any list of scores into probabilities that add up to 1 using eˣ. Its roots go back to Boltzmann (1868).
- **Linear Regression**: Legendre and Gauss (1805–1809). Fit a line to data by minimizing error, the first "learning from data".

### Artificial Intelligence
- **Turing Test (1950)**: Turing asks "can machines think?" and proposes the imitation game.
- **Dartmouth Workshop (1956)**: McCarthy, Minsky and Shannon (a callback) name the field "artificial intelligence".
- **Perceptron (1958)**: Rosenblatt's machine learns to classify by adjusting weights. The first artificial neuron that learns.
- **AI Winters (1970s)**: Minsky and Papert show a single perceptron can't learn XOR (a callback to the XOR gate), promises fail, and funding dries up.
- **Backpropagation (1986)**: Rumelhart, Hinton and Williams train multi-layer networks with the chain rule, and XOR is solved.
- **Convolutional Neural Network (1989)**: LeCun's network reads handwritten zip codes by sliding small filters over images.
- **LSTM (1997)**: Hochreiter and Schmidhuber give networks a long memory for sequences like text and speech, much like a flip-flop for neural networks.
- **ImageNet (2009)**: Fei-Fei Li's 14 million labeled images, the big dataset deep learning needed.
- **Deep Learning (2012)**: AlexNet wins ImageNet by a huge margin with a deep CNN on GPUs. Data, GPUs and backprop finally come together.
- **Word2Vec (2013)**: Mikolov turns words into vectors, so king − man + woman ≈ queen.
- **Attention (2014)**: Bahdanau and colleagues let a translation model look back at the most relevant words instead of squeezing everything into one memory.
- **AlphaGo (2016)**: DeepMind beats Lee Sedol at Go using deep networks and reinforcement learning.
- **Transformer (2017)**: "Attention Is All You Need" drops recurrence and uses only attention, so it runs in parallel on GPUs.
- **RLHF (2017)**: Christiano and colleagues train a model from human judgments of which output is better.
- **GPT (2018)**: OpenAI pretrains a transformer to predict the next word on lots of text. GPT-2 and GPT-3 scale it up.
- **ChatGPT (2022)**: GPT + RLHF as a chat, and LLMs reach everyone.

### Machine Learning
- **Neuron**: a weighted sum of inputs plus a bias, passed through an activation. The perceptron as a math function (a dot product).
- **Neural Network**: layers of neurons. One layer is matrix × vector, and a forward pass goes through all the layers.
- **Activation Function**: why non-linearity is needed (step, sigmoid, ReLU). Without it, many layers collapse into one.
- **Loss Function**: one number for "how wrong". Mean squared error and cross-entropy (which uses log and probability).
- **Training**: backprop computes gradients with the chain rule, gradient descent updates the weights, and this repeats over the data in batches and epochs.
- **Generalization**: training vs test data, and overfitting vs underfitting. Memorizing vs learning.
- **Convolution**: slide a small filter over pixels to detect edges and shapes. Stacked layers build up to whole objects.
- **Reinforcement Learning**: learning by trial and error. Agent, action, reward and policy, with AlphaGo as the example.
- **Tokenization**: split text into tokens (pieces of words) and give each an ID. A callback to Text as Numbers.
- **Embeddings**: each token ID becomes a learned vector, and similar meanings end up close together (Word2Vec).
- **Recurrent Neural Network**: read one token at a time while carrying a hidden state as memory. Why it forgets and is slow, leading to LSTM.
- **Self-Attention**: each token makes query, key and value vectors. Dot products and softmax decide which other tokens to pay attention to.
- **Transformer Block**: attention + a feed-forward network + residual connections + layer normalization (statistics), stacked many times.
- **Next-Token Prediction**: the last layer scores every token, softmax turns the scores into probabilities, one token is picked, and it repeats. This is how an LLM writes.
- **Training an LLM**: pretraining on huge amounts of web text, the scale of data, parameters and GPUs, and scaling laws.
- **Fine-Tuning and RLHF**: instruction examples, humans ranking answers, a reward model, and reinforcement learning. How a base model becomes an assistant.
- **Running an LLM**: inference. Weights sit in GPU memory, matrix multiplications run in parallel, the context window, the cost, and data centers.

### Robotics
- **Governor (1788)**: Watt's spinning balls control a steam engine's speed. The first automatic feedback controller.
- **Robot (1920)**: Čapek's play *R.U.R.* coins "robot", from the Czech "robota" (forced labor).
- **Three Laws of Robotics (1942)**: Asimov's fictional rules for robot behavior. The first popular idea of rules for a machine's behavior.
- **Cybernetics (1948)**: Wiener's science of control and communication in animals and machines. Feedback is everywhere.
- **Unimate (1961)**: the first industrial robot arm, handling hot metal parts at a General Motors plant.
- **Shakey (1966)**: SRI's mobile robot that could see, plan and move. The first to combine robotics with AI.
- **WABOT-1 (1973)**: Waseda University's first full-scale humanoid, able to walk, grip and talk.
- **ASIMO (2000)**: Honda's humanoid that walks smoothly and climbs stairs.
- **Roomba (2002)**: iRobot's vacuum cleaner brings robots into homes.
- **DARPA Grand Challenge (2005)**: Stanford's Stanley drives 212 km of desert by itself, the start of self-driving cars.
- **Robot Operating System (2007)**: an open-source framework so robot builders can share drivers, tools and algorithms.
- **Robot Foundation Models (2023)**: large models trained on web and robot data (such as RT-2) let robots follow spoken instructions.

### Robot Engineering
- **Actuators**: what moves a robot. DC, servo and stepper motors, gears, torque vs speed, and motor drivers (H-bridge, PWM).
- **Sensors**: what a robot feels. Rotary encoders, the IMU (accelerometer, gyroscope), distance sensors and cameras, read through an ADC.
- **Feedback Control**: open loop vs closed loop. Measure, compare with the goal, and correct (a Watt's governor callback).
- **PID Controller**: proportional, integral and derivative terms that control a motor's position smoothly, with a tuning example.
- **Kinematics**: from joint angles to where the hand is, using trig and rotation matrices.
- **Inverse Kinematics**: the reverse, from a target position to joint angles. There can be many solutions or none.
- **Dynamics**: the forces and torques needed to move the arm (Newton): mass, inertia and gravity.
- **Motion Planning**: finding a path that avoids obstacles, with graph search (A*) and sampling (RRT).
- **Localization and Mapping**: "Where am I, and what's around me?" Odometry, sensor fusion and SLAM, using probability.
- **Computer Vision**: robots see through cameras. CNNs detect and recognize objects, and depth is estimated.
- **Robot Learning**: learning skills with reinforcement learning in simulation, or by imitating human demonstrations.
- **Vision-Language-Action Model**: one transformer takes a camera image and a spoken instruction and outputs robot actions.

### AI Safety and Alignment
- **The Alignment Problem**: getting AI to do what we *mean*, not what we literally wrote. Wiener's 1960 warning and the King Midas story.
- **Reward Hacking**: models exploit the reward instead of reaching the goal, like a boat-racing AI that spins in circles collecting points.
- **Hallucination**: next-token prediction produces fluent but false answers. Why it happens and how to reduce it.
- **Adversarial Attacks**: tiny pixel changes that fool vision models, jailbreaks, and prompt injection.
- **Interpretability**: looking inside networks to see what neurons and features represent. The one abstraction we can't fully look under yet.
- **Evaluation and Red Teaming**: benchmarks, tests for dangerous abilities, and people trying to break the model before release.
- **Robot Safety**: emergency stops, force limits, safety zones, and standards for robots working near people.
- **Full Circle**: trace one request ("robot, pick up the cup") down through the LLM, the GPU, transistors and gates to 0 and 1, back to yes or no.
