## Problem — Who is affected, and what specifically breaks down for them today?

Food insecurity is a major issue in the Bay Area, particularly in Oakland, and aligns with UN SDG 1: No Poverty and UN SDG 2: Zero Hunger. The specific population affected in this project is single mothers in Oakland working part-time jobs who cannot consistently afford groceries due to high rent, unstable income, and transportation costs.

Our persona, Maria, is a single mother who needs food assistance for herself and her children. The failure point is not the absence of resources, but the inability to access them effectively. Food banks, CalFresh, and community programs exist, but the information is scattered across different websites, eligibility requirements are confusing, and there is no clear next step. Maria cannot easily find, understand, or act on the available support, which causes the system to break down at the point of decision-making.

## AI Capability — Which lab capability addresses the failure point, and why does it fit?

Lab 2: Structured Data Extraction directly addresses the failure point by converting a resident’s unstructured message into structured data fields such as location, need type, urgency, and appropriate service. This fits the problem because Maria should not have to search across multiple systems; instead, the AI interprets her request and prepares it for immediate action.

Lab 3: Image Recognition + Civic Analysis supports the system by allowing users to analyze images of food distribution sites, community centers, or flyers. The AI identifies the problem, explains its impact, determines urgency, and recommends action. However, this capability is dependent on correct image input and is less reliable in low-resource situations, which limits its standalone effectiveness.

## Workflow — What goes in, what does the AI do, what comes out, and who acts on the output? Include screenshots of output

Input:
Maria enters a message such as:
“I am a single mother in Oakland and need free groceries this week.”

AI processing:
The AI extracts important details from the message, including:

Location: Oakland
Assistance type: food assistance/free groceries
Urgency: high
Recommended department/service: food bank or social services
Resident language: English

Output:
The system returns a structured summary of Maria’s situation, urgency level, recommended service type, and a plain-language next step.

{
  "location": "Oakland",
  "need_type": "food",
  "urgency": "high",
  "support_type": "food bank",
  "eligibility_notes": "low-income households may qualify"
}
^^Example structured output based on Lab 2 schema demonstrating how the system extracts key information from a user request.

<img width="1449" height="486" alt="Screenshot 2026-05-10 at 8 42 51 PM" src="https://github.com/user-attachments/assets/efc49522-b2b0-435c-93b4-f8a47c218ef0" />

Image analysis output showing how the system identifies the problem, impact, urgency, and recommended action from a visual input.

Real-world action:
Maria uses the output to contact a food bank, apply for CalFresh, visit a food distribution site, or call a city/community service. A social worker, food bank staff member, or city service worker could also use the output to quickly route her request.

## Failure Case — One specific failure, with a reference to the lab output that showed it is possible.

A key failure occurs in the image analysis workflow (Lab 3). When the system attempts to analyze an image, it fails if the image file is not available or properly uploaded. In our prototype, the output produced an error indicating that the image file could not be found.
This demonstrates that the system depends on correct technical input, which may not be realistic for users like Maria, who may have limited access to devices, time, or technical skills. As shown in the Lab 3 output, the system can break before analysis even begins, making it unreliable as a primary method of assistance.

## Oversight and Tradeoff — Where does human review sit, and what does the one change cost?

Human oversight should be introduced after the AI generates structured outputs, especially for high-urgency cases. A social worker, food bank staff member, or city service representative should review cases where users indicate immediate need, lack of transportation, or language barriers.

One key change is adding a human review step for urgent cases. This improves reliability and ensures that vulnerable users receive appropriate and accessible recommendations. However, the tradeoff is increased cost and slower response time, as human involvement requires staffing and reduces the speed of automated processing. Despite this, the added oversight is necessary to prevent critical failures in high-risk situations.
