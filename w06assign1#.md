What a backend is:
In simple terms, the backend is the invisible engine or server-side logic that lives on a remote computer (server). While the frontend is what users see and click on your screen, the backend handles the hidden tasks—like receiving data, processing requests, talking to databases, or routing a contact form message safely to an email inbox without exposing private keys or code.

What my feature does:
My portfolio features a live, working contact form. When a visitor types their email and message and clicks "Send," the feature captures that input, validates it, and successfully triggers a real submission that lands directly in my personal inbox. It transforms the portfolio from a static poster into an interactive communication tool.

How the data flows:

Input (Frontend): The user fills out the form fields (email and message) right inside the browser interface and clicks the submit button.

Transit (API Request): The browser packages this data securely and sends an HTTP POST request over the internet to the backend endpoint hosted by Formspree (our free-tier service provider).

Processing & Delivery (Backend): Formspree receives the payload, processes the parameters, filters out spam, and routes the message data using backend mail servers.

Output (Result): A formatted email notification instantly arrives in my inbox containing the user's message, completing the end-to-end loop.