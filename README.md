#Inspiration
Detecting deceit can be invaluable in numerous situations - from evaluating the credibility of a politician to determining the innocence of a suspected criminal. Nevertheless, current systems that are designed to detect lies, such as polygraph machines or EEG systems, are high-cost and very constrained as far as the tests they support. The idea behind this project was to create a tool capable of instantly evaluating the truth of a given audio clip in an efficient, cost-effective manner.

#What it does
Lie2Me is a software solution that relies heavily on signal processing and machine learning. Users upload an audio clip of someone speaking, which is then broken down into several relevant features, like spectral data and MFCCs. The model then produces summary statistics that concisely represent the aforementioned features. These revised features are then fed into various machine learning models (two-class neural networks were determined to be the most effective) to produce a class prediction corresponding to truth or falsehood.

#How we built it
Given the lack of publicly available audio data for lie detection, we had to go about collecting data ourselves. We first created a questionnaire and then interviewed ten American-born males to collect audio samples, with the subjects providing information about whether or not they were telling the truth. Subjects were told to lie for five of the ten questions asked and tell the truth for the others without predetermining how they would answer. These audio responses were saved and converted to .wav files, before being processed with the open source PyAudioAnalysis library. After generating summary statistics for the feature vectors produced by the audio analysis and matching them with corresponding binary labels, we used Azure ML Studio to evaluate different machine learning models and identify the best one for our use case. Progress is currently underway to embed the functionality of this work into a web and mobile app.

#Challenges we ran into
Collecting data was the first major hurdle we faced, in large part because there is no precedent for how to accurately obtain information on whether people are telling the truth. Thus, formulating the questionnaire and actually administering it proved very challenging. Additionally, we ran into some issues with compatibility with some of the libraries we chose to use, requiring us to downgrade to previous releases of Python (2.7) and some of its important libraries.

#Accomplishments that we're proud of
Despite a relatively crude dataset, whose sample size was limited by time and resources, we were still able to obtain a generalized test accuracy of up to ~70% - far superior to a simple random guess. Furthermore, the fact that we were able to figure out and implement the feature extraction part of our work was particularly satisfying since neither of us had previously worked with audio data before.

#What we learned
This was the first Hackathon for both of us, and we learned just how motivating and frustrating building a hack can be. Through our methods, we both gained familiarity with Azure, as well as other standard data analysis tools. We found Azure very straightforward to use and will continue taking advantage of its features for our future endeavors. As with any team project, we also gained a lot from the opportunity to talk out ideas and bugs together.

#What's next for Lie2Me
The next step of this work involves integrating what we have built with a web or mobile app to facilitate its use. Also, we would love to collect more data to make our models more robust, which would hopefully push our already-promising accuracy even higher. The most exciting aspect of this work, however, is the large scope that it covers. There is so much that can be done as far as exploring different models, methods of feature extraction, and metrics of success, meaning that there is plenty of room for optimization. Overall, we feel that this is an incredibly promising area that has a lot of future potential.
