<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tech-Communication Rules & Regulations</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', 'Helvetica', sans-serif;
            background: #2c3e50;
            padding: 20px;
            color: #333;
        }
        
        .pdf-container {
            max-width: 210mm;
            margin: 0 auto;
            background: white;
            box-shadow: 0 8px 40px rgba(0,0,0,0.4);
            position: relative;
        }
        
        .pdf-page {
            width: 210mm;
            min-height: 297mm;
            padding: 15mm;
            position: relative;
            background: white;
            page-break-after: always;
        }
        
        /* Technical Background Pattern */
        .pdf-page::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(102, 126, 234, 0.05) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(118, 75, 162, 0.05) 0%, transparent 50%),
                linear-gradient(90deg, rgba(102, 126, 234, 0.02) 1px, transparent 1px),
                linear-gradient(rgba(102, 126, 234, 0.02) 1px, transparent 1px);
            background-size: 100% 100%, 100% 100%, 20px 20px, 20px 20px;
            pointer-events: none;
            z-index: 0;
        }
        
        /* Code symbols decoration */
        .code-symbol {
            position: absolute;
            font-family: 'Courier New', monospace;
            font-weight: bold;
            opacity: 0.03;
            z-index: 0;
        }
        
        .code-symbol.top-left {
            top: 40px;
            left: 20px;
            font-size: 120px;
            color: #667eea;
        }
        
        .code-symbol.top-right {
            top: 30px;
            right: 30px;
            font-size: 100px;
            color: #764ba2;
        }
        
        .code-symbol.bottom-left {
            bottom: 50px;
            left: 30px;
            font-size: 90px;
            color: #667eea;
        }
        
        .code-symbol.bottom-right {
            bottom: 40px;
            right: 20px;
            font-size: 110px;
            color: #764ba2;
        }
        
        .content {
            position: relative;
            z-index: 1;
        }
        
        /* Header */
        .pdf-header {
            text-align: center;
            padding: 25px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            margin: -15mm -15mm 20px -15mm;
            color: white;
            position: relative;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
        }
        
        .pdf-header::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 0;
            right: 0;
            height: 10px;
            background: linear-gradient(to bottom, rgba(102, 126, 234, 0.2), transparent);
        }
        
        .header-icon {
            font-size: 50px;
            margin-bottom: 10px;
            filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.3));
        }
        
        .pdf-title {
            font-size: 38px;
            font-weight: bold;
            margin-bottom: 8px;
            letter-spacing: 1px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        
        .pdf-subtitle {
            font-size: 24px;
            font-weight: 300;
            opacity: 0.95;
        }
        
        /* Section Styling */
        .pdf-section {
            margin-bottom: 25px;
            background: #f8f9fa;
            padding: 18px;
            border-radius: 8px;
            border-left: 5px solid #667eea;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }
        
        .section-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid #e9ecef;
        }
        
        .section-icon {
            font-size: 26px;
        }
        
        .section-title {
            font-size: 20px;
            font-weight: bold;
            color: #667eea;
        }
        
        .rule-list {
            list-style: none;
        }
        
        .rule-item {
            padding-left: 22px;
            margin-bottom: 10px;
            position: relative;
            line-height: 1.6;
            color: #2c3e50;
            font-size: 14px;
        }
        
        .rule-item::before {
            content: "►";
            position: absolute;
            left: 0;
            color: #764ba2;
            font-size: 12px;
        }
        
        .rule-item strong {
            color: #667eea;
        }
        
        /* Table Styling */
        .criteria-table-container {
            margin-top: 15px;
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        
        .criteria-table {
            width: 100%;
            border-collapse: collapse;
            background: white;
        }
        
        .criteria-table thead {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        
        .criteria-table th {
            padding: 14px;
            text-align: left;
            font-weight: bold;
            font-size: 15px;
        }
        
        .criteria-table td {
            padding: 12px 14px;
            border-bottom: 1px solid #e9ecef;
            font-size: 14px;
        }
        
        .criteria-table tbody tr:nth-child(even) {
            background: #f8f9fa;
        }
        
        .criteria-table tbody tr:last-child {
            background: #667eea15;
            font-weight: bold;
            color: #667eea;
        }
        
        /* Rewards Grid */
        .rewards-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 15px;
        }
        
        .reward-box {
            background: white;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 3px 12px rgba(0,0,0,0.1);
            border: 2px solid #e9ecef;
            transition: all 0.3s;
        }
        
        .reward-box:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.3);
        }
        
        .reward-medal {
            font-size: 50px;
            margin-bottom: 10px;
        }
        
        .reward-position {
            font-size: 16px;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 8px;
        }
        
        .reward-points {
            font-size: 26px;
            font-weight: bold;
            color: #764ba2;
        }
        
        /* Warning Box */
        .warning-section {
            background: linear-gradient(135deg, #fff3cd 0%, #ffeaa7 100%);
            border: 3px solid #ffc107;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 25px;
            box-shadow: 0 3px 12px rgba(255, 193, 7, 0.2);
        }
        
        .warning-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 12px;
        }
        
        .warning-icon {
            font-size: 28px;
        }
        
        .warning-title {
            font-size: 20px;
            font-weight: bold;
            color: #d39e00;
        }
        
        /* Notice Box */
        .notice-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 22px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
            margin-top: 25px;
        }
        
        .notice-icon {
            font-size: 32px;
            margin-bottom: 8px;
        }
        
        .notice-title {
            font-size: 22px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .notice-text {
            font-size: 14px;
            line-height: 1.6;
            opacity: 0.95;
        }
        
        /* Footer */
        .pdf-footer {
            position: absolute;
            bottom: 10mm;
            left: 15mm;
            right: 15mm;
            text-align: center;
            font-size: 11px;
            color: #95a5a6;
            padding-top: 15px;
            border-top: 1px solid #e9ecef;
        }
        
        /* Print Styles */
        @media print {
            body {
                background: white;
                padding: 0;
            }
            
            .pdf-container {
                box-shadow: none;
                max-width: 100%;
            }
            
            .pdf-page {
                width: 100%;
                margin: 0;
                box-shadow: none;
            }
            
            .reward-box:hover {
                transform: none;
            }
        }
        
        @page {
            size: A4;
            margin: 0;
        }
    </style>
</head>
<body>
    <div class="pdf-container">
        <div class="pdf-page">
            <!-- Technical Background Symbols -->
            <div class="code-symbol top-left">&lt;/&gt;</div>
            <div class="code-symbol top-right">{ }</div>
            <div class="code-symbol bottom-left">[ ]</div>
            <div class="code-symbol bottom-right">( )</div>
            
            <div class="content">
                <!-- Header -->
                <div class="pdf-header">
                    <div class="header-icon">📜</div>
                    <div class="pdf-title">RULES & REGULATIONS</div>
                    <div class="pdf-subtitle">Tech-Communication Event</div>
                </div>
                
                <!-- General Rules Section -->
                <div class="pdf-section">
                    <div class="section-header">
                        <span class="section-icon">🔹</span>
                        <span class="section-title">General Rules</span>
                    </div>
                    <ul class="rule-list">
                        <li class="rule-item">Teams must register before the deadline — late entries won't be accepted.</li>
                        <li class="rule-item">The speaking order will be determined by lot system.</li>
                        <li class="rule-item">Participants must be present 10 minutes before the event begins.</li>
                        <li class="rule-item">Polite and professional communication is compulsory.</li>
                        <li class="rule-item">Organizers and Staff members decision is final and binding. (We ensure fair distribution of points based on review of event).</li>
                        <li class="rule-item">No breaks during the event are allowed.</li>
                    </ul>
                </div>
                
                <!-- Speaking Guidelines Section -->
                <div class="pdf-section">
                    <div class="section-header">
                        <span class="section-icon">🔹</span>
                        <span class="section-title">Speaking Guidelines</span>
                    </div>
                    <ul class="rule-list">
                        <li class="rule-item">Maximum <strong>10-15 minutes</strong> per team (including transitions).</li>
                        <li class="rule-item">Exceeding time will lead to negative marking.</li>
                        <li class="rule-item">Only one person speaks at a time — no interruptions.</li>
                        <li class="rule-item">Content should be technically accurate, structured, and original.</li>
                        <li class="rule-item">Use of formal language and clear pronunciation is expected.</li>
                        <li class="rule-item">Teams may divide the topic into parts (e.g., introduction, explanation, conclusion).</li>
                    </ul>
                </div>
                
                <!-- Mandatory Regulations Section -->
                <div class="pdf-section">
                    <div class="section-header">
                        <span class="section-icon">🔹</span>
                        <span class="section-title">Mandatory Regulations</span>
                    </div>
                    <ul class="rule-list">
                        <li class="rule-item">Mobile phones must be switched off during the event.</li>
                        <li class="rule-item">Reading directly from paper or phone will lead to disqualification.</li>
                        <li class="rule-item">Participants must maintain discipline and decorum throughout.</li>
                    </ul>
                </div>
                
                <!-- Judging Criteria Section -->
                <div class="pdf-section">
                    <div class="section-header">
                        <span class="section-icon">🏆</span>
                        <span class="section-title">Judging Criteria</span>
                    </div>
                    <div class="criteria-table-container">
                        <table class="criteria-table">
                            <thead>
                                <tr>
                                    <th>Criteria</th>
                                    <th style="text-align: center; width: 100px;">Marks</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>Technical content & accuracy</td>
                                    <td style="text-align: center;">25</td>
                                </tr>
                                <tr>
                                    <td>Clarity and fluency</td>
                                    <td style="text-align: center;">20</td>
                                </tr>
                                <tr>
                                    <td>Confidence and body language</td>
                                    <td style="text-align: center;">15</td>
                                </tr>
                                <tr>
                                    <td>Team coordination</td>
                                    <td style="text-align: center;">15</td>
                                </tr>
                                <tr>
                                    <td>Creativity & originality</td>
                                    <td style="text-align: center;">15</td>
                                </tr>
                                <tr>
                                    <td>Time management</td>
                                    <td style="text-align: center;">10</td>
                                </tr>
                                <tr>
                                    <td><strong>Total</strong></td>
                                    <td style="text-align: center;"><strong>100</strong></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
                
                <!-- Rewards Section -->
                <div class="pdf-section">
                    <div class="section-header">
                        <span class="section-icon">🥇</span>
                        <span class="section-title">Rewards & Points</span>
                    </div>
                    <div class="rewards-grid">
                        <div class="reward-box">
                            <div class="reward-medal">🥇</div>
                            <div class="reward-position">1st Place</div>
                            <div class="reward-points">100 Points</div>
                        </div>
                        <div class="reward-box">
                            <div class="reward-medal">🥈</div>
                            <div class="reward-position">2nd Place</div>
                            <div class="reward-points">50 Points</div>
                        </div>
                        <div class="reward-box">
                            <div class="reward-medal">🥉</div>
                            <div class="reward-position">3rd Place</div>
                            <div class="reward-points">25 Points</div>
                        </div>
                    </div>
                </div>
                
                <!-- Tie-Breaker Section -->
                <div class="pdf-section">
                    <div class="section-header">
                        <span class="section-icon">⚖️</span>
                        <span class="section-title">Tie-Breaker Rule</span>
                    </div>
                    <p style="margin-bottom: 10px; font-style: italic; color: #666; font-size: 14px;">In case two or more teams score the same total marks:</p>
                    <ul class="rule-list">
                        <li class="rule-item">Judges will conduct a tie-breaker round.</li>
                        <li class="rule-item">Each tied team will be given a new surprise technical topic.</li>
                        <li class="rule-item">Teams will have <strong>1 minute to prepare</strong> and <strong>5 minutes to speak</strong>.</li>
                        <li class="rule-item">Judges will evaluate based on content clarity, confidence, and creativity only.</li>
                        <li class="rule-item">The tie-breaker score will determine the final places.</li>
                    </ul>
                </div>
                
                <!-- Disqualification Warning -->
                <div class="warning-section">
                    <div class="warning-header">
                        <span class="warning-icon">⚠️</span>
                        <span class="warning-title">Disqualification Grounds</span>
                    </div>
                    <ul class="rule-list">
                        <li class="rule-item">Use of phones, written notes, or internet while speaking.</li>
                        <li class="rule-item">Offensive or non-technical content.</li>
                        <li class="rule-item">Exceeding time limit by more than 1 minute.</li>
                        <li class="rule-item">Ignoring team/speaking rules or showing disrespect to judges.</li>
                    </ul>
                </div>
                
                <!-- Important Notice -->
                <div class="notice-section">
                    <div class="notice-icon">📢</div>
                    <div class="notice-title">Notice to All Participants</div>
                    <div class="notice-text">
                        All participants are strictly advised to read the following rules and regulations thoroughly before the competition. Non-compliance with any rule may lead to penalty or disqualification.
                    </div>
                </div>
            </div>
            
            <!-- Footer -->
            <div class="pdf-footer">
                Tech-Communication Event | Official Rules & Regulations Document
            </div>
        </div>
    </div>
</body>
</html>
