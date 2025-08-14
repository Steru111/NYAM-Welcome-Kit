<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NYAM Welcome Kits</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            color: white;
        }
        
        .header h1 {
            font-size: 3em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        
        .header p {
            font-size: 1.2em;
            opacity: 0.95;
        }
        
        .tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .tab-button {
            padding: 15px 30px;
            background: white;
            border: none;
            border-radius: 50px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            font-weight: 600;
        }
        
        .tab-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.15);
        }
        
        .tab-button.active {
            background: #2c3e50;
            color: white;
        }
        
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .tab-content.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .welcome-kit {
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .kit-header {
            border-bottom: 3px solid #2c3e50;
            padding-bottom: 20px;
            margin-bottom: 30px;
        }
        
        .kit-header h2 {
            color: #2c3e50;
            font-size: 2.5em;
            margin-bottom: 10px;
        }
        
        .membership-badge {
            display: inline-block;
            padding: 8px 20px;
            border-radius: 25px;
            font-weight: bold;
            text-transform: uppercase;
            font-size: 0.9em;
            letter-spacing: 1px;
            margin-bottom: 15px;
        }
        
        .badge-fellow {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
        }
        
        .badge-member {
            background: linear-gradient(135deg, #2196F3, #1976D2);
            color: white;
        }
        
        .badge-student {
            background: linear-gradient(135deg, #4CAF50, #388E3C);
            color: white;
        }
        
        .section {
            margin-bottom: 35px;
        }
        
        .section h3 {
            color: #2c3e50;
            font-size: 1.6em;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .section h3::before {
            content: '▸';
            color: #667eea;
            font-size: 1.2em;
        }
        
        .welcome-message {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 20px;
        }
        
        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .benefit-card {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 12px;
            border-left: 4px solid #667eea;
            transition: transform 0.3s ease;
        }
        
        .benefit-card:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .benefit-card h4 {
            color: #2c3e50;
            margin-bottom: 10px;
            font-size: 1.1em;
        }
        
        .benefit-card p {
            color: #666;
            font-size: 0.95em;
        }
        
        .exclusive-badge {
            display: inline-block;
            background: #ff6b6b;
            color: white;
            padding: 3px 8px;
            border-radius: 5px;
            font-size: 0.8em;
            font-weight: bold;
            margin-left: 5px;
        }
        
        .action-items {
            background: #f0f4f8;
            padding: 25px;
            border-radius: 12px;
            margin-top: 20px;
        }
        
        .action-items ol {
            padding-left: 20px;
        }
        
        .action-items li {
            margin-bottom: 15px;
            color: #2c3e50;
        }
        
        .contact-box {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 25px;
            border-radius: 12px;
            margin-top: 20px;
        }
        
        .contact-box h4 {
            margin-bottom: 15px;
            font-size: 1.3em;
        }
        
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .contact-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 8px;
        }
        
        .contact-item h5 {
            margin-bottom: 8px;
            font-size: 1.1em;
        }
        
        .contact-item a {
            color: white;
            text-decoration: none;
            border-bottom: 1px dotted rgba(255, 255, 255, 0.5);
        }
        
        .contact-item a:hover {
            border-bottom-color: white;
        }
        
        .important-date {
            background: #fff3cd;
            border: 2px solid #ffc107;
            padding: 20px;
            border-radius: 12px;
            margin: 20px 0;
            text-align: center;
        }
        
        .important-date h4 {
            color: #856404;
            margin-bottom: 10px;
        }
        
        .important-date p {
            color: #856404;
            font-size: 1.1em;
            font-weight: 600;
        }
        
        .quick-links {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 20px;
        }
        
        .quick-link {
            display: inline-block;
            padding: 10px 20px;
            background: #2c3e50;
            color: white;
            text-decoration: none;
            border-radius: 8px;
            transition: all 0.3s ease;
        }
        
        .quick-link:hover {
            background: #34495e;
            transform: translateY(-2px);
        }
        
        @media (max-width: 768px) {
            .welcome-kit {
                padding: 25px;
            }
            
            .kit-header h2 {
                font-size: 2em;
            }
            
            .benefits-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>NYAM</h1>
            <p>Welcome to The New York Academy of Medicine</p>
        </div>
        
        <div class="tabs">
            <button class="tab-button active" onclick="showTab('fellow')">Fellow Kit</button>
            <button class="tab-button" onclick="showTab('member')">Member Kit</button>
            <button class="tab-button" onclick="showTab('student')">Student Member Kit</button>
        </div>
        
        <!-- FELLOW WELCOME KIT -->
        <div id="fellow" class="tab-content active">
            <div class="welcome-kit">
                <div class="kit-header">
                    <span class="membership-badge badge-fellow">Fellow</span>
                    <h2>Welcome to Fellowship at NYAM</h2>
                    <p style="font-size: 1.2em; color: #666;">An honor recognizing your distinguished achievements in advancing health equity</p>
                </div>
                
                <div class="section">
                    <div class="welcome-message">
                        <h3 style="margin-bottom: 20px;">Welcome Message</h3>
                        <p>Dear Fellow,</p>
                        <p style="margin-top: 15px;">Congratulations on your election to Fellowship at The New York Academy of Medicine. This prestigious recognition reflects your exceptional contributions to health and medicine, and your commitment to advancing health equity for all.</p>
                        <p style="margin-top: 15px;">As a Fellow, you join a distinguished community of nearly 2,000 leaders who have demonstrated excellence in practice, research, education, administration, or public service. Your expertise and engagement are vital to our mission of building healthspan—ensuring that all people have what they need for not only longer, but also healthier lives.</p>
                        <p style="margin-top: 15px; font-weight: 600;">— Ann Kurth, PhD, CNM, MPH<br>President, The New York Academy of Medicine</p>
                    </div>
                </div>
                
                <div class="important-date">
                    <h4>Save the Date</h4>
                    <p>December 1st, 2025</p>
                    <p style="font-size: 1em; font-weight: 400; margin-top: 10px;">177th Anniversary Discourse & Annual Meeting<br>Your Formal Induction Ceremony</p>
                </div>
                
                <div class="section">
                    <h3>Your Fellowship Benefits</h3>
                    <div class="benefits-grid">
                        <div class="benefit-card">
                            <h4>Professional Recognition <span class="exclusive-badge">FELLOW EXCLUSIVE</span></h4>
                            <p>Prestigious fellowship designation elected by peers, commemorative certificate, membership pin, and official card recognizing your distinguished achievements.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Journal of Urban Health <span class="exclusive-badge">FELLOW EXCLUSIVE</span></h4>
                            <p>Complimentary quarterly subscription to our peer-reviewed journal addressing critical urban health challenges and policy perspectives.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Royal Society of Medicine <span class="exclusive-badge">FELLOW EXCLUSIVE</span></h4>
                            <p>Discounted overseas membership to the Royal Society of Medicine, expanding your international professional network.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Leadership Opportunities <span class="exclusive-badge">FELLOW PRIORITY</span></h4>
                            <p>Serve in Academy Sections, nominate candidates for prestigious awards, and shape NYAM's strategic initiatives.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>World-Class Library Access</h4>
                            <p>Priority access to 550,000+ volumes, rare manuscripts, historical collections, and personalized research assistance from expert librarians.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Professional Development</h4>
                            <p>Free or discounted access to 100+ annual events, symposia, and continuing education programs across disciplines.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Digital Platform Access</h4>
                            <p>Exclusive online portal with job board, member directory, profile management tools, and specialized resources.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Networking Excellence</h4>
                            <p>Connect with leading clinicians, researchers, and policy makers through interdisciplinary Sections and specialized workgroups.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Grant Opportunities</h4>
                            <p>Access to $400,000+ in annual research grants and fellowships supporting innovative health studies and initiatives.</p>
                        </div>
                    </div>
                </div>
                
                <div class="section">
                    <h3>Getting Started: Your Action Items</h3>
                    <div class="action-items">
                        <ol>
                            <li><strong>Pay Your Annual Dues ($250)</strong><br>
                            You'll receive a secure payment link via email. Dues support our collective mission and maintain your active status.</li>
                            
                            <li><strong>Complete Your Online Profile</strong><br>
                            Visit the Fellows Portal at nyam.org to update your information and set your directory preferences.</li>
                            
                            <li><strong>Join Academy Sections</strong><br>
                            Select from 13+ interdisciplinary and specialty Sections aligned with your interests and expertise.</li>
                            
                            <li><strong>Access Library Resources</strong><br>
                            Activate your library privileges for in-person and remote access to collections and databases.</li>
                            
                            <li><strong>Mark Your Calendar</strong><br>
                            December 1st, 2025 - Your formal induction at the Annual Meeting (details to follow).</li>
                            
                            <li><strong>Explore Engagement Opportunities</strong><br>
                            Review upcoming events, committees, and initiatives where your expertise can make an impact.</li>
                        </ol>
                    </div>
                </div>
                
                <div class="section">
                    <h3>Quick Access Links</h3>
                    <div class="quick-links">
                        <a href="https://nyam.org/fellows" class="quick-link">Fellows Portal</a>
                        <a href="https://nyam.org/library" class="quick-link">Library Access</a>
                        <a href="https://nyam.org/sections" class="quick-link">Join Sections</a>
                        <a href="https://nyam.org/events" class="quick-link">Upcoming Events</a>
                        <a href="https://nyam.org/grants" class="quick-link">Grant Opportunities</a>
                    </div>
                </div>
                
                <div class="contact-box">
                    <h4>Your Support Team</h4>
                    <div class="contact-grid">
                        <div class="contact-item">
                            <h5>Fellows Office</h5>
                            <p>Connor Bellis, Director</p>
                            <p>📧 <a href="mailto:fellows@nyam.org">fellows@nyam.org</a></p>
                            <p>📞 (212) 822-7367</p>
                        </div>
                        <div class="contact-item">
                            <h5>General Inquiries</h5>
                            <p>📧 <a href="mailto:info@nyam.org">info@nyam.org</a></p>
                            <p>🌐 <a href="https://nyam.org">www.nyam.org</a></p>
                            <p>📞 (212) 822-7200</p>
                        </div>
                        <div class="contact-item">
                            <h5>Visit Us</h5>
                            <p>The New York Academy of Medicine</p>
                            <p>1216 Fifth Avenue</p>
                            <p>New York, NY 10029</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- MEMBER WELCOME KIT -->
        <div id="member" class="tab-content">
            <div class="welcome-kit">
                <div class="kit-header">
                    <span class="membership-badge badge-member">Member</span>
                    <h2>Welcome to Membership at NYAM</h2>
                    <p style="font-size: 1.2em; color: #666;">Join our community of health professionals driving innovation and equity</p>
                </div>
                
                <div class="section">
                    <div class="welcome-message">
                        <h3 style="margin-bottom: 20px;">Welcome Message</h3>
                        <p>Dear Member,</p>
                        <p style="margin-top: 15px;">Welcome to The New York Academy of Medicine! Your membership represents an important step in your professional journey and a commitment to advancing health equity in our communities.</p>
                        <p style="margin-top: 15px;">As a Member, you join a vibrant network of health professionals at various career stages, all united in our mission to ensure everyone has the opportunity to live a healthy life. Your fresh perspectives and emerging expertise are essential to driving innovation in public health.</p>
                        <p style="margin-top: 15px; font-weight: 600;">— Ann Kurth, PhD, CNM, MPH<br>President, The New York Academy of Medicine</p>
                    </div>
                </div>
                
                <div class="important-date">
                    <h4>Save the Date</h4>
                    <p>December 1st, 2025</p>
                    <p style="font-size: 1em; font-weight: 400; margin-top: 10px;">Annual Meeting & Awards Presentation<br>Your Formal Induction Ceremony</p>
                </div>
                
                <div class="section">
                    <h3>Your Membership Benefits</h3>
                    <div class="benefits-grid">
                        <div class="benefit-card">
                            <h4>Professional Recognition</h4>
                            <p>Official membership designation, commemorative certificate, membership pin, and card recognizing your commitment to health equity.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Career Development</h4>
                            <p>Access to comprehensive job board, career resources, and mentorship opportunities to advance your professional growth.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Library Resources</h4>
                            <p>Full access to our world-renowned medical library with 550,000+ volumes and expert research assistance.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Educational Programs</h4>
                            <p>Free or significantly discounted registration to 100+ annual events, webinars, and continuing education programs.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Networking Platform</h4>
                            <p>Connect with established professionals and peers through Sections, workgroups, and special interest committees.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Digital Resources</h4>
                            <p>Exclusive member portal with profile tools, resource library, and priority communications about opportunities.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Section Participation</h4>
                            <p>Join interdisciplinary and specialty Sections to engage with colleagues in your areas of interest.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Research Opportunities</h4>
                            <p>Information about grant opportunities and collaborative research initiatives in urban health.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Leadership Development</h4>
                            <p>Opportunities to serve on committees, contribute to initiatives, and develop leadership skills.</p>
                        </div>
                    </div>
                </div>
                
                <div class="section">
                    <h3>Getting Started: Your Action Items</h3>
                    <div class="action-items">
                        <ol>
                            <li><strong>Pay Your Annual Dues ($125)</strong><br>
                            Watch for your secure payment link via email. Your dues support our programs and maintain your active status.</li>
                            
                            <li><strong>Set Up Your Online Profile</strong><br>
                            Visit the Members Portal to complete your profile and connect with the community.</li>
                            
                            <li><strong>Select Your Sections</strong><br>
                            Choose from our diverse Sections to engage with professionals in your field of interest.</li>
                            
                            <li><strong>Explore the Job Board</strong><br>
                            Access exclusive career opportunities and resources in the healthcare sector.</li>
                            
                            <li><strong>Register for Events</strong><br>
                            Browse upcoming programs and register with your member discount.</li>
                            
                            <li><strong>Activate Library Access</strong><br>
                            Set up your library privileges for research support and resource access.</li>
                        </ol>
                    </div>
                </div>
                
                <div class="section">
                    <h3>Quick Access Links</h3>
                    <div class="quick-links">
                        <a href="https://nyam.org/members" class="quick-link">Members Portal</a>
                        <a href="https://nyam.org/jobs" class="quick-link">Job Board</a>
                        <a href="https://nyam.org/sections" class="quick-link">Join Sections</a>
                        <a href="https://nyam.org/events" class="quick-link">Events Calendar</a>
                        <a href="https://nyam.org/library" class="quick-link">Library Resources</a>
                    </div>
                </div>
                
                <div class="contact-box">
                    <h4>Your Support Team</h4>
                    <div class="contact-grid">
                        <div class="contact-item">
                            <h5>Membership Services</h5>
                            <p>📧 <a href="mailto:fellows@nyam.org">fellows@nyam.org</a></p>
                            <p>📞 (212) 822-7272</p>
                        </div>
                        <div class="contact-item">
                            <h5>General Support</h5>
                            <p>📧 <a href="mailto:info@nyam.org">info@nyam.org</a></p>
                            <p>🌐 <a href="https://nyam.org">www.nyam.org</a></p>
                            <p>📞 (212) 822-7200</p>
                        </div>
                        <div class="contact-item">
                            <h5>Location</h5>
                            <p>1216 Fifth Avenue</p>
                            <p>New York, NY 10029</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- STUDENT MEMBER WELCOME KIT -->
        <div id="student" class="tab-content">
            <div class="welcome-kit">
                <div class="kit-header">
                    <span class="membership-badge badge-student">Student Member</span>
                    <h2>Welcome to Student Membership at NYAM</h2>
                    <p style="font-size: 1.2em; color: #666;">Launch your career in health with mentorship and opportunities</p>
                </div>
                
                <div class="section">
                    <div class="welcome-message">
                        <h3 style="margin-bottom: 20px;">Welcome Message</h3>
                        <p>Dear Student Member,</p>
                        <p style="margin-top: 15px;">Welcome to The New York Academy of Medicine! Your student membership marks the beginning of an exciting journey in health and medicine, connecting you with leaders who will inspire and guide your career.</p>
                        <p style="margin-top: 15px;">As a Student Member, you gain unique access to mentorship, educational resources, and networking opportunities that will shape your professional development. You represent the future of healthcare, and we're committed to supporting your growth.</p>
                        <p style="margin-top: 15px; font-weight: 600;">— Ann Kurth, PhD, CNM, MPH<br>President, The New York Academy of Medicine</p>
                    </div>
                </div>
                
                <div class="important-date">
                    <h4>Welcome Event</h4>
                    <p>Student & Residents' Night</p>
                    <p style="font-size: 1em; font-weight: 400; margin-top: 10px;">Annual networking and career development event<br>Date TBA - Watch for your invitation</p>
                </div>
                
                <div class="section">
                    <h3>Your Student Membership Benefits</h3>
                    <div class="benefits-grid">
                        <div class="benefit-card">
                            <h4>Career Launch Support</h4>
                            <p>Exclusive access to job board with entry-level positions, internships, and residency opportunities in healthcare.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Mentorship Access</h4>
                            <p>Connect with established Fellows and Members who can guide your career development and provide insights.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Student Programs</h4>
                            <p>Special events including Student & Residents' Nights designed for networking and professional development.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Educational Resources</h4>
                            <p>Free or heavily discounted access to lectures, webinars, and symposia across health disciplines.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Library Privileges</h4>
                            <p>Full access to research materials, databases, and librarian assistance for your academic work.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Grant Opportunities</h4>
                            <p>Information about student research grants including the David E. Rogers Fellowship and other funding.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Networking Platform</h4>
                            <p>Build relationships with peers and professionals through Sections and online member directory.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Professional Development</h4>
                            <p>Workshops and resources on career planning, CV building, and transitioning to professional practice.</p>
                        </div>
                        <div class="benefit-card">
                            <h4>Future Pathway</h4>
                            <p>Clear progression to full Membership upon graduation, maintaining your NYAM connections.</p>
                        </div>
                    </div>
                </div>
                
                <div class="section">
                    <h3>Getting Started: Your Action Items</h3>
                    <div class="action-items">
                        <ol>
                            <li><strong>Pay Your Annual Dues ($25)</strong><br>
                            Watch for your secure payment link. This affordable rate makes membership accessible during your studies.</li>
                            
                            <li><strong>Verify Your Student Status</strong><br>
                            Ensure your school has confirmed your enrollment in good standing.</li>
                            
                            <li><strong>Create Your Profile</strong><br>
                            Set up your online account to access all digital resources and the member directory.</li>
                            
                            <li><strong>Explore Career Resources</strong><br>
                            Check the job board regularly for internships and entry-level opportunities.</li>
                            
                            <li><strong>Join a Section</strong><br>
                            Connect with professionals in your field of interest through our specialty Sections.</li>
                            
                            <li><strong>Attend Student Events</strong><br>
                            Mark your calendar for Student & Residents' Nights and other special programs.</li>
                        </ol>
                    </div>
                </div>
                
                <div class="section">
                    <h3>Student Resources</h3>
                    <div class="quick-links">
                        <a href="https://nyam.org/students" class="quick-link">Student Portal</a>
                        <a href="https://nyam.org/jobs" class="quick-link">Internships & Jobs</a>
                        <a href="https://nyam.org/grants/student" class="quick-link">Student Grants</a>
                        <a href="https://nyam.org/events/students" class="quick-link">Student Events</a>
                        <a href="https://nyam.org/library" class="quick-link">Research Support</a>
                    </div>
                </div>
                
                <div class="contact-box">
                    <h4>Student Support</h4>
                    <div class="contact-grid">
                        <div class="contact-item">
                            <h5>Student Services</h5>
                            <p>📧 <a href="mailto:students@nyam.org">students@nyam.org</a></p>
                            <p>📞 (212) 822-7272</p>
                        </div>
                        <div class="contact-item">
                            <h5>Career Support</h5>
                            <p>📧 <a href="mailto:careers@nyam.org">careers@nyam.org</a></p>
                            <p>🌐 <a href="https://nyam.org/careers">Career Center</a></p>
                        </div>
                        <div class="contact-item">
                            <h5>Visit NYAM</h5>
                            <p>1216 Fifth Avenue</p>
                            <p>New York, NY 10029</p>
                            <p>Student tours available</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        function showTab(tabName) {
            // Hide all tab contents
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(content => content.classList.remove('active'));
            
            // Remove active class from all buttons
            const buttons = document.querySelectorAll('.tab-button');
            buttons.forEach(button => button.classList.remove('active'));
            
            // Show selected tab
            document.getElementById(tabName).classList.add('active');
            
            // Add active class to clicked button
            event.target.classList.add('active');
        }
    </script>
</body>
</html>
