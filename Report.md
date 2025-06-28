
# 📘 Technical Report: AI-Powered Hybrid Exam Proctoring System

## 1.0 Problem Statement

Remote education has expanded globally, but millions of students in rural or under-connected areas cannot access online exams effectively. Most current systems require stable internet and real-time cloud processing, excluding underserved communities.

Furthermore, exam integrity is at risk when supervision is absent or insufficient, resulting in widespread cheating or impersonation.

---

## 2.0 Proposed Solution

We present a **hybrid proctoring platform** that:

- Works **offline** using local device resources
- Uses **AI (face detection & eye tracking)** to monitor students
- Syncs data securely when internet returns
- Generates detailed **reports and behavioral analytics**

---

## 3.0 System Architecture

### a. Frontend
- Built with React and TailwindCSS
- Includes exam interface, webcam feed, exam timer, and status indicators

### b. AI Monitoring
- Uses TensorFlow.js + BlazeFace to track:
  - Face presence
  - Eye direction
  - Suspicious behavior (multiple faces, screen switch)

### c. Offline Mode
- Exams stored in `IndexedDB`
- Monitoring logs recorded locally
- Auto-sync feature triggers on `navigator.onLine = true`

### d. Backend
- Node.js & Express server
- MongoDB stores student answers, exam metadata, and logs
- RESTful APIs for exam retrieval, submission, and reporting

### e. Analytics
- Chart.js & D3.js generate:
  - Time-per-question graphs
  - Cheating probability scores
  - Flagged behavior summaries

---

## 4.0 Implementation Plan

| Step | Description                            |
|------|----------------------------------------|
| 1    | Setup frontend project using CRA       |
| 2    | Implement AI model for webcam analysis |
| 3    | Build offline answer storage with IndexedDB |
| 4    | Sync engine with retry mechanism       |
| 5    | Create backend routes & DB models      |
| 6    | Generate educator dashboard with charts|
| 7    | Simulate exams in low-bandwidth cases  |

---

## 5.0 Testing Strategy

- ✅ Functional test: AI triggers alerts on head turning / no face
- ✅ Offline test: Disconnect mid-exam and resume sync
- ✅ Performance test: System on low RAM/CPU mobile device
- ✅ Edge test: More than one face detected

---

## 6.0 Impact & Benefits

- **Inclusivity**: Makes digital exams possible in underserved regions
- **Integrity**: Prevents cheating without human proctors
- **Scalability**: Works across schools, gov orgs, and mobile apps
- **Affordability**: Low infrastructure cost; open-source model

---

## 7.0 Limitations

- In-browser AI may be limited by device CPU
- Syncing large video files in low-bandwidth can delay uploads
- Not a full replacement for in-person invigilation (yet)

---

## 8.0 Future Enhancements

- Add voice recognition to detect spoken cheating
- Enable biometric login (face match at start)
- Integrate WebSockets for live flag updates
- Build native Android APK using React Native

---

## 9.0 Conclusion

This platform addresses two of the most pressing issues in remote education: **accessibility** and **exam integrity**. By leveraging edge AI and offline capabilities, it ensures students everywhere can take exams fairly—even with poor or no internet.

---

📧 For collaborations or deployment interest, contact the project maintainer or open an issue on GitHub.
