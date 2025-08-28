<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); padding: 3rem 2rem; border-radius: 20px; margin-bottom: 2rem; color: white; text-align: center; position: relative; overflow: hidden;">
  <div style="position: absolute; top: -50px; right: -50px; width: 100px; height: 100px; background: rgba(255,255,255,0.1); border-radius: 50%;"></div>
  <div style="position: absolute; bottom: -30px; left: -30px; width: 60px; height: 60px; background: rgba(255,255,255,0.1); border-radius: 50%;"></div>
  
  <h1 style="color: white; margin: 0; font-size: 2.5rem; text-shadow: 2px 2px 4px rgba(0,0,0,0.3);">
    💡 Technical Excellence
  </h1>
  <p style="font-size: 1.3rem; margin: 1rem 0 0 0; color: rgba(255,255,255,0.9); font-style: italic;">
    Sections 11-15 from the original journey • Advanced Systems & Innovation
  </p>
</div>

<div style="position: relative; margin-left: 3rem;">
  <div style="position: absolute; left: -3rem; top: 0; bottom: 0; width: 4px; background: linear-gradient(to bottom, #16a085, #c0392b, #27ae60, #d35400, #2ecc71); border-radius: 2px;"></div>

  <div style="background: linear-gradient(135deg, #16a085 0%, #1abc9c 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #16a085; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">11</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">💡 Innovation in Notification Reliability</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The pull notifications experiment from my internship days evolved into a comprehensive solution for notification reliability. Modern mobile operating systems are increasingly aggressive about limiting background processing, meaning traditional push notifications sometimes fail to reach users even when their devices are online.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        I designed and implemented a sophisticated system to handle this challenge. Background workers on Android and BGAppRefreshTasks on iOS would periodically refresh device tokens and check for missed notifications. When the app couldn't run these background tasks, we would send silent push notifications to trigger the refresh process.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The backend component I built could scan our Aerospike database for tokens that hadn't been refreshed recently, identify users who might have missed notifications, and intelligently send silent pushes to wake up their apps. The system was capable of processing 230,000 events per minute while making complex decisions about user behavior patterns and notification delivery success rates.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📱</div>
        <strong style="color: white;">Android Workers</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🍎</div>
        <strong style="color: white;">iOS BGAppRefresh</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔔</div>
        <strong style="color: white;">Silent Push</strong>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">⚡ Performance:</strong> 230,000 events per minute with intelligent user behavior pattern analysis
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #c0392b 0%, #e74c3c 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #c0392b; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">12</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🔧 Problem-Solving & Issue Resolution</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Not every challenge was about building new systems. A significant part of my role involved diagnosing and resolving critical issues that could impact client functionality. Here are a couple of examples:
      </p>
    </div>

    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px;">
        <div style="text-align: center; margin-bottom: 1rem;">
          <div style="font-size: 2rem; margin-bottom: 0.5rem;">📱</div>
          <strong style="color: white; display: block;">Android Compatibility Issue</strong>
        </div>
        <p style="color: rgba(255,255,255,0.9); font-size: 0.9rem; margin: 0;">
          When a client upgraded their Google Ads Identifier library to version 18.2.0, Android 7 devices started crashing. The investigation revealed that the newer library was using Java 8 APIs like `java.time.Duration` that didn't exist on older Android versions. I provided solutions including core library desugaring and documented the process for future reference.
        </p>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px;">
        <div style="text-align: center; margin-bottom: 1rem;">
          <div style="font-size: 2rem; margin-bottom: 0.5rem;">🌐</div>
          <strong style="color: white; display: block;">Arabic Text Encoding Issue</strong>
        </div>
        <p style="color: rgba(255,255,255,0.9); font-size: 0.9rem; margin: 0;">
          We encountered a problem where Arabic text was being displayed as gibberish to users. The issue stemmed from a change in the format that clients were sending Arabic text, and our decoding logic wasn't handling the new format properly. I fixed the decoding implementation to work robustly across different text formats, ensuring proper display of Arabic content.
        </p>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">🎯 Impact:</strong> These are just two issues I remember from the many bugs and technical challenges I've diagnosed and resolved throughout my time at the company.
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #27ae60 0%, #2ecc71 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #27ae60; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">13</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🏗️ The Infrastructure Behind the Code</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Throughout this journey, I was also learning the operational side of software development. I dockerized applications, managed Kubernetes deployments through Devtron, and maintained the complex web of services that kept everything running. Setting up monitoring with Prometheus and Grafana, optimizing Aerospike queries with User Defined Functions, and managing certificate rotations for FCM and APNS might not be glamorous work, but it's the foundation that allows the exciting features to actually function reliably.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🐳</div>
        <strong style="color: white;">Docker</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">☸️</div>
        <strong style="color: white;">Kubernetes</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📊</div>
        <strong style="color: white;">Prometheus</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📈</div>
        <strong style="color: white;">Grafana</strong>
      </div>
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #d35400 0%, #e67e22 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #d35400; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">14</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🛡️ Security Hardening and Trust</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Working with financial services clients meant that security couldn't be an afterthought. I implemented certificate pinning for iOS SDK API calls, designed secure token management systems, and ensured that every piece of sensitive data was handled with appropriate encryption and access controls. These weren't just technical requirements – they were about building systems that clients could trust with their most sensitive communications.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📌</div>
        <strong style="color: white;">Certificate Pinning</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔐</div>
        <strong style="color: white;">Token Management</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🛡️</div>
        <strong style="color: white;">Access Controls</strong>
      </div>
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #8e44ad 0%, #9b59b6 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #8e44ad; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">15</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🌟 Looking Forward: From Journey to Destination</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        As I reflect on this journey from intern to full-time engineer, what strikes me most is how each challenge built upon the previous ones. The debugging skills I learned during on-call rotations helped me optimize performance bottlenecks. The cross-platform SDK work prepared me for thinking about system architecture. The infrastructure improvements taught me to think beyond just writing code to understanding the complete operational picture.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        I've gone from someone who needed tutorials to understand Spring Boot to someone who can design and implement systems that handle hundreds of thousands of events per minute. I've learned to balance the demands of high-performance systems with the reliability requirements of financial services. I've experienced the satisfaction of both finding critical bugs and building entirely new capabilities.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        But perhaps most importantly, I've learned that great engineering isn't just about writing clever code – it's about understanding problems deeply, designing sustainable solutions, and building systems that other people can depend on. Every notification that reaches a user's device, every system that stays up during peak traffic, every bug that gets fixed before it impacts production – these are the real measures of success.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; text-align: center;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0; font-size: 1.1rem; font-weight: bold;">
        The journey continues, and I'm ready for whatever challenges come next.
      </p>
    </div>
  </div>

</div>

## 📊 Technical Achievements Summary

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; margin: 2rem 0;">
  <div style="background: linear-gradient(135deg, #3498db, #2980b9); padding: 1.5rem; border-radius: 12px; text-align: center; color: white;">
    <div style="font-size: 2.5rem; margin-bottom: 0.5rem;">⚡</div>
    <h3 style="margin: 0.5rem 0; color: white;">30x Performance</h3>
    <p style="margin: 0; font-size: 0.9rem; opacity: 0.9;">From 5K to 150K+ notifications/min</p>
  </div>
  
  <div style="background: linear-gradient(135deg, #e74c3c, #c0392b); padding: 1.5rem; border-radius: 12px; text-align: center; color: white;">
    <div style="font-size: 2.5rem; margin-bottom: 0.5rem;">🎯</div>
    <h3 style="margin: 0.5rem 0; color: white;">99.7% Reliability</h3>
    <p style="margin: 0; font-size: 0.9rem; opacity: 0.9;">Notification delivery success rate</p>
  </div>
  
  <div style="background: linear-gradient(135deg, #2ecc71, #27ae60); padding: 1.5rem; border-radius: 12px; text-align: center; color: white;">
    <div style="font-size: 2.5rem; margin-bottom: 0.5rem;">🏗️</div>
    <h3 style="margin: 0.5rem 0; color: white;">Complete Rebuild</h3>
    <p style="margin: 0; font-size: 0.9rem; opacity: 0.9;">Node.js to Java Spring Boot</p>
  </div>
  
  <div style="background: linear-gradient(135deg, #f39c12, #e67e22); padding: 1.5rem; border-radius: 12px; text-align: center; color: white;">
    <div style="font-size: 2.5rem; margin-bottom: 0.5rem;">🔒</div>
    <h3 style="margin: 0.5rem 0; color: white;">Banking Security</h3>
    <p style="margin: 0; font-size: 0.9rem; opacity: 0.9;">Enterprise-grade encryption</p>
  </div>
</div>

## 🛠️ Core Technologies Mastered

<div style="background: linear-gradient(135deg, #34495e, #2c3e50); padding: 2rem; border-radius: 12px; color: white; margin: 2rem 0;">
  <h3 style="color: white; margin-top: 0;">Full-Stack Technology Expertise</h3>
  <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin-top: 1.5rem;">
    <div style="background: rgba(255,255,255,0.1); padding: 1rem; border-radius: 8px;">
      <h4 style="color: #3498db; margin-top: 0;">Backend</h4>
      <p style="margin: 0; opacity: 0.9;">Java Spring Boot, Node.js, Microservices Architecture</p>
    </div>
    <div style="background: rgba(255,255,255,0.1); padding: 1rem; border-radius: 8px;">
      <h4 style="color: #e74c3c; margin-top: 0;">Infrastructure</h4>
      <p style="margin: 0; opacity: 0.9;">Kubernetes, Docker, AWS, Jenkins CI/CD</p>
    </div>
    <div style="background: rgba(255,255,255,0.1); padding: 1rem; border-radius: 8px;">
      <h4 style="color: #2ecc71; margin-top: 0;">Data & Messaging</h4>
      <p style="margin: 0; opacity: 0.9;">Kafka, Redis, PostgreSQL, MongoDB</p>
    </div>
    <div style="background: rgba(255,255,255,0.1); padding: 1rem; border-radius: 8px;">
      <h4 style="color: #f39c12; margin-top: 0;">Monitoring</h4>
      <p style="margin: 0; opacity: 0.9;">Prometheus, Grafana, ELK Stack</p>
    </div>
  </div>
</div>

---

<div style="text-align: center; margin: 3rem 0; padding: 2rem; background: #f8f9fa; border-radius: 12px;">
  <h3 style="color: #2c3e50; margin-bottom: 1rem;">Complete Journey Navigation</h3>
  <p style="color: #7f8c8d; margin-bottom: 2rem;">Explore the full story of growth and transformation</p>
  
  <div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;">
    <a href="lemnisk_internship.html" style="background: #3498db; color: white; padding: 1rem 2rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
      🌱 Internship Story
    </a>
    <a href="lemnisk_fulltime.html" style="background: #9b59b6; color: white; padding: 1rem 2rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
      🚀 Full-Time Journey
    </a>
    <a href="lemnisk_overview.html" style="background: #95a5a6; color: white; padding: 1rem 2rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
      📊 Back to Overview
    </a>
  </div>
</div>
