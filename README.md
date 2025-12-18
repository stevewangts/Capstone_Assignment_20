### Project Title : Optimizing Team Composition: A Machine Learning Approach to Identifying High-Potential Female Mountain Bike Athletes

**Yu Wang**

#### Executive summary
Executive Summary: Data-Driven Recruitment for Female Student Athletes

Project Title
Optimizing Team Composition: A Machine Learning Approach to Identifying 
High-Potential Female Mountain Bike Athletes1.
 
1. The Challenge
	The High School Mountain Bike Club faces a significant gender disparity, 
	with female participation consistently lagging behind male enrollment. 
	Traditional "blanket" recruitment strategies (e.g., general announcements, 
	flyers) have yielded insufficient results and place an unsustainable strain
	on limited volunteer resources. The club lacks a systematic method to identify 
	which students are most likely to enjoy and succeed in the sport.

2. The Objective
    To transition from a passive recruitment model to a proactive, data-driven 
	strategy. By leveraging historical trends and student performance metrics, 
	the project aims to:
		Identify female students with high latent potential for success in mountain biking.
		Prioritize recruitment efforts toward candidates with the highest probability of retention.
		Ultimately achieve a balanced and competitive team roster.

3. Methodology
     We developed a Machine Learning Recruitment Pipeline to analyze student attributes and predict 
	 a "Recruitment Potential Score."Data Synthesis: Due to privacy constraints and data scarcity, 
	 we generated a robust synthetic dataset of 300 female students.
	 Key Metrics Analyzed: The model evaluates academic discipline (GPA), cardiovascular endurance 
	 (Mile Time), prior athletic background (Cross Country, Soccer), and logistical factors 
	 (Access to Bike).Modeling Technique: We established a baseline using Linear Regression to 
	 quantify how these variables correlate with potential success in the club.

4. Initial Findings & Performance:
     Predictive Capability: The initial baseline model achieved an $R^2$ score of 0.45, meaning 
	 the current variables successfully explain approximately 45% of the variance in a recruit's 
	 potential.Key Indicators: Early analysis suggests that cardiovascular baselines (Mile Time) 
	 and complementary sports backgrounds (specifically Cross Country and Track) are strong predictors 
	 of high potential scores.
	 
5. Strategic Recommendations
     Based on preliminary data, the club should shift its focus from general recruitment to targeted 
	 outreach:Cross-Sport Partnership: collaborative recruiting with Cross Country and Track coaches
	 during their off-seasons.Resource Allocation: Focus "Loaner Bike" inventory on high-potential 
	 athletes who lack equipment (Access_To_Bike = 0),as this is a solvable barrier to entry.Targeted
	 Outreach: Use the model to generate a "Top 20" list of candidates for personalized invitations rather than mass emails.

6. Next Steps
    Model Refinement: Upgrade from Linear Regression to Ridge Regression or Random Forest 
	algorithms to improve prediction accuracy beyond the 45% baseline.Pilot Program: Test the 
	"Top 20" prediction list in the upcoming semester to validate real-world conversion rates.
	Does this summary capture the tone you were looking for? I can make it more technical 
	(for a data science portfolio) or more persuasive (for a funding grant) if you prefer.

#### Rationale
Why should anyone care about this question?

1. The Practical Case: Resource Efficiency
	"Stop Spraying and Praying." Most high school clubs run on volunteer hours and shoestring 
	budgets. The current strategy ("blanket recruitment") is expensive in terms of time and 
	effort. Why it matters: By identifying the specific attributes of successful female riders, 
	the club stops wasting energy trying to recruit students who have zero interest or aptitude.
	The Value: It transforms recruitment from a marketing problem (shouting at everyone) into a 
	targeting problem (talking to the right people).

2. The Competitive Case: Finding "Hidden Talent"
	"The Moneyball Effect." There are students in the school who have high aerobic capacity 
	(from gym class mile times) or grit (from academic discipline) but do not identify as 
	"athletes" because they don't fit the mold of traditional varsity sports like soccer or 
	basketball.Why it matters: These students are "undervalued assets." They have the engine to 
	be state champions but have never been asked to ride a bike.The Value: This model identifies 
	high-potential athletes before they join, giving the team a competitive edge over schools that 
	only rely on students showing up voluntarily.

3. The Social Case: Closing the Gender Gap
	"Equity requires Intentionality." The gender gap in cycling is well-documented. Passive recruitment
	often reinforces the status quo (mostly boys join because their friends joined).Why it matters: 
	Research shows that girls drop out of sports at twice the rate of boys by age 14. A generic invite
	is often ignored by female students who don't see themselves represented.The Value: A data-driven 
	approach allows for personalized invitations. When a coach says, "I noticed you ran a great mile 
	time and have a strong GPA; we think you'd be a team leader," it changes the narrative from "You 
	can join if you want" to "We specifically want you."

4. The Educational Case: Lifelong Wellness
	"Connecting Students to their 'Thing'." Mountain biking is a lifelong sport, unlike many varsity
	sports that end after high school.Why it matters: There are students who are disengaged from school
	culture because they haven't found their "tribe." The Value: By using data to find students who need
	this outlet (perhaps high energy, high drive, but no current sport), the school fulfills its mission 
	of student wellness and engagement.
	
	
	We care about this question because identifying the right student 
	is the difference between a struggling club and a championship team that changes lives.

#### Research Question
What are you trying to answer?

	The project is fundamentally trying to answer one core strategic question:
	"What are the specific, measurable attributes (demographic, academic, and athletic) that predict 
	whether a female student will be a successful and persistent member of the Mountain Bike Club?"

	To break that down, the project seeks to answer these specific sub-questions using data:
	The Athletic Indicator: Does a fast mile time (aerobic base) or experience in specific sports 
	(like Cross Country or Soccer) strongly correlate with success in mountain biking?

	The Academic Indicator: Is there a relationship between academic discipline (GPA) and the ability
	to stick with a demanding endurance sport?

	The Logistical Barrier: How much does "Access to a Bike" or "Having a Sibling in the Club" influence 
	a student's potential score?

	The Prediction: Can we feed a new student's data into a model and get a reliable "Recruit Score" 
	that tells us who to prioritize?

	In short: We are trying to find the "DNA" of a successful female recruit so we can find more students
	who match that profile.

#### Data Sources
What data will you use to answer you question?
	To answer the project's core question, we will use the Synthetic Historical Roster Data that we 
	generated. In a real-world scenario, this would represent anonymized data compiled from the last
	3–5 years of school athletic records and club rosters.
	
	Here is the breakdown of the specific data points (features) we are using and why each one matters 
	for answering our question:
    
	1. The Dataset Overview
		File Name: high_school_mtb_recruits.csv
		Volume: 300 Data Points (representing individual female students).
		Target Variable: Recruit_Potential_Score (0–100). This is the "answer key"—a score combining
		retention, race performance, and coachability.
	
	2. The Specific Variables (Features)
	   We are using three categories of data to predict success:
			
			A. Physical & Athletic Metrics 
			
				Mile_Time_Min (Numerical): 
					What it is: The time it takes the student to run a mile (e.g., 7.5 min).
					Why we use it: Mountain biking is an endurance sport. This is our primary proxy for aerobic 
					capacity (VO2 Max). We hypothesize that lower mile times correlate with higher success.

				Weekly_Exercise_Hours (Numerical):
					What it is: Self-reported hours of physical activity per week.
					Why we use it: Measures general fitness habituation. A student who already exercises 
					5+ hours a week will have an easier transition than one who is sedentary.

				Previous_Sport (Categorical):
					What it is: The main sport the student played previously (e.g., Soccer, Cross 
					Country, Track, Basketball, None).
					Why we use it: Identifies transferable skills. We suspect "Cross Country" (endurance)
					and "Soccer" (interval endurance) transfers better than "None."

			B. Academic & Behavioral Metrics 
			
				GPA (Numerical):
					What it is: Grade Point Average (2.0 – 4.0).
					Why we use it: Measures discipline and grit. Mountain biking requires consistent effort 
					over long periods. High academic performers often possess the "delayed gratification" mindset 
					needed for endurance sports.

				Grade_Level (Categorical):
					What it is: Freshman (9) through Senior (12).
					Why we use it: Helps us understand if we should target younger students (for longevity
					in the program) or older students (for immediate maturity).

			C. Logistical & Social Metrics

				Access_To_Bike (Binary: 0 or 1):
					What it is: Does the student already own or have access to a mountain bike?
					Why we use it: Identifying barriers to entry. A high-potential student without a bike needs 
					a "Loaner Bike" scholarship; otherwise, they won't join.

				Has_Sibling_In_Club (Binary: 0 or 1):
					What it is: Does the student have a brother or sister already on the team?
					Why we use it: A strong predictor of recruitment conversion. Siblings lower the 
					"social anxiety" barrier of joining a new club.

	Summary of Data Flow
		We feed these Inputs (A, B, C) into our machine learning models (Linear, Ridge, etc.) to learn 
		the mathematical relationship between them and the Target (Recruit Potential Score).

#### Methodology
What methods are you using to answer the question?
	To answer the question "Who are the high-potential female recruits?", we are using a method called 
	Supervised Regression Analysis.

	1. The Core Technique: Supervised Learning
	   We are using Supervised Learning because we have a "labeled" dataset.
	   The Input: We show the model the attributes of students (GPA, Mile Time, Previous Sport).
	   The Answer Key: We show the model their actual historical success (Recruit_Potential_Score).
	   The Goal: The model learns the formula so that when it sees a new student (without a score), it can calculate one.

	2. The Algorithms (The "Math Engines")
		We are using two distinct algorithms to ensure we get the best possible prediction.
		
		Method A: Linear Regression (The "Baseline")
			What it does: It draws a straight line through the data. It assumes a simple relationship: 
			"If Mile Time goes down by 1 minute, Score goes up by X points."

			Why we use it: It is highly interpretable. It tells us exactly how much each factor matters.
			For example, it might tell us that "Running Cross Country" is worth exactly +10 points.

		Method B: Random Forest Regression (The "Advanced" Model)
			What it does: Instead of one line, it builds hundreds of "Decision Trees" (flowcharts) 
			that ask questions like: "Is her mile time under 8:00? If yes, does she play Soccer? 
			If yes, Score is high."

			Why we use it: It captures non-linear relationships. For example, maybe having a bike helps,
			but only if you also have a sibling on the team. Linear regression misses this; Random Forest
			catches it.

	3. Feature Engineering (Data Prep)
		Before the math happens, we transform the raw data to make it usable:
		
		One-Hot Encoding: Converting text data like "Soccer" or "Basketball" into numbers 
		(0s and 1s) so the math equations can process them.

		Scaling: We adjust ranges so that GPA (scale 0-4) doesn't look "smaller" or less important 
		than Mile Time (scale 6-12) just because the numbers are smaller.
		
	4. Validation (The "BS Check")
		We don't trust the model blindly. We use a method called Train-Test Split:Training (80%): 
		We let the model study 240 students to learn the patterns.Testing (20%): We hide the scores 
		of the remaining 60 students and ask the model to guess them.Comparison: We compare the model's 
		guess to reality. If the $R^2$ Score is high (close to 1.0), the method works.

#### Results
What did your research find?
	Our analysis of the 300-student dataset yielded three critical findings regarding the High School 
	Mountain Bike Club's recruitment potential.
	
	1. The "Cardio Correlation" is the Strongest Predictor
	   Our research found that aerobic capacity is the single most dominant indicator of a student's 
	   potential success in the club.
	   
		Finding: 
			Mile_Time_Min accounted for ~34% of the predictive power in our models.
		Translation: 
			A student who runs a fast mile (indicating a strong aerobic engine) is mathematically highly 
			likely to succeed in mountain biking, regardless of their prior experience with a bike.
	    Actionable Insight: 
			The club should prioritize recruiting from the Cross Country and Track teams, or students 
			who perform well in the "timed mile" during PE classes.
	
	2. The "Access Barrier" is Significant
	   We discovered that logistical factors play a huge role, often outweighing pure athletic ability.
			
		Finding: Access_To_Bike was the 3rd most important feature (~14% importance), nearly equal to 
			Weekly_Exercise.
		
		Translation: There is a "hidden talent pool" of students who have the fitness (High GPA, Fast Mile) 
			but simply lack a bike. The model penalizes their score heavily because they currently have no means
			to participate.
		
		Actionable Insight: This validates the need for a "Loaner Bike Program." If the club provides a bike,
			they unlock a massive segment of high-potential athletes who are currently ignored.
	
	3. Simpler Models Work Best (The "Moneyball" Insight)We tested three different Artificial Intelligence models
	   to see which could best predict a recruit's potential.
	   
			Linear Regression ($R^2 = 0.45$): Good.
			Ridge Regression ($R^2 = 0.45$): Best. (Slightly better at handling data noise).
			Random Forest ($R^2 = 0.36$): Worse.The Takeaway: T
			he relationship between attributes and success is linear and direct. We don't need complex, 
			"black box" AI. A simple checklist or scorecard (e.g., Points for Mile Time + Points for GPA) 
			will be highly effective and easy for coaches to use without a computer.Summary of "The Perfect 
			Recruit"Based on the data, the ideal candidate profile—the student we should aggressively 
			recruit—looks like this:Mile Time: < 8:30 minutes.Current Sport: Cross Country or Soccer 
			(or none, but high general exercise).GPA: > 3.0 (demonstrating the discipline to stick with 
			a hard sport).Barrier: May or may not own a bike (this is where the club steps in).Would you 
			like to see the "Scorecard" I can generate based on these findings? (I can create a simple 
			PDF-style checklist for you to print).

#### Next steps
What suggestions do you have for next steps?

	Based on our findings that aerobic capacity (Mile Time) and resource access (Bike Ownership) 
	are the biggest drivers of potential, here are three concrete recommendations for your next steps.

	1. The Strategic Step: Operationalize the "Recruit Scorecard"
	   Since our Ridge Regression model worked best (and is simple), we can translate the math into 
	   a physical checklist for coaches. We don't need a laptop at the track meet; we just need a 
	   scorecard. 
	   
	   Proposal: I can generate a printable PDF-style "Scouting Report".
       
	   How it works: It converts the regression coefficients into points.
			Mile Time under 8:00? +10 Points. GPA above 3.5? +5 Points. Does not own a bike? Flag for Scholarship.
	   Why: This bridges the gap between "Data Science" and "Field Work."

	2. The Data Science Step: Build a "Recruitment Calculator"
	   If you want to keep coding, the next logical step is to build a tool that makes predictions 
	   on new data.

	   Proposal: We can build a simple interactive function or a Streamlit Web App.

		How it works: You enter a student's stats (e.g., "Jane Doe, 9th Grade, 7:45 Mile, No Bike"),
		and the model outputs: "Candidate Priority: High (Predicted Score: 88/100)."

		Why: This allows the team manager to input a spreadsheet of 50 interested students and instantly
		get a sorted priority list.

	3. The Business Case: The "Loaner Bike" Proposal
	   The data showed that Access_To_Bike was a major factor. If a student has high potential but no bike,
	   the model predicts a lower score unless the barrier is removed.

	   Proposal: Use the data to simulate a "What If" scenario.

	   How it works: We re-run the model for the top 20 "No Bike" students but flip their Access_To_Bike
	   variable from 0 to 1.

	   Why: If their predicted scores jump significantly, you have mathematical proof to present to
	   the school board: "Investing $5,000 in 5 loaner bikes will unlock 5 Varsity-level athletes."
	   
#### Outline of project

- [Link to notebook 1]()
- [Link to notebook 2]()
- [Link to notebook 3]()


##### Contact and Further Information