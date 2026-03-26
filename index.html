import { useState, useEffect, useRef } from "react";

const SCREENS = {
  HOOK: "hook",
  QUIZ: "quiz",
  REVEAL: "reveal",
  PITCH: "pitch",
};

const fakeCandidates = [
  {
    name: "Candidate A",
    selfReport: { teamwork: 95, leadership: 90, adaptability: 88, integrity: 97 },
    reality: { teamwork: 41, leadership: 28, adaptability: 55, integrity: 34 },
    redFlags: ["Passive-aggressive in group threads", "Takes credit for others' ideas", "Avoids conflict by ghosting"],
    chatExcerpt: `"lol yeah I'll handle it" → (never handles it)\n"that was basically my idea" → (it wasn't)\n"sure, sounds great 👍" → (complains privately to 3 people)`,
  },
  {
    name: "Candidate B",
    selfReport: { teamwork: 92, leadership: 85, adaptability: 91, integrity: 94 },
    reality: { teamwork: 78, leadership: 82, adaptability: 69, integrity: 88 },
    redFlags: ["Micromanages when stressed", "Struggles to delegate", "Over-promises timelines"],
    chatExcerpt: `"I'll just do it myself, faster that way"\n"Can you send me a screenshot of your progress?"\n"We can definitely ship by Friday" → (they cannot)`,
  },
];

function GlitchText({ children, className = "" }) {
  const [glitch, setGlitch] = useState(false);
  useEffect(() => {
    const interval = setInterval(() => {
      setGlitch(true);
      setTimeout(() => setGlitch(false), 150);
    }, 3000 + Math.random() * 4000);
    return () => clearInterval(interval);
  }, []);
  return (
    <span className={className} style={{ position: "relative", display: "inline-block" }}>
      {children}
      {glitch && (
        <>
          <span style={{ position: "absolute", left: "2px", top: "-1px", color: "#ff003c", opacity: 0.7, clipPath: "inset(10% 0 60% 0)" }}>{children}</span>
          <span style={{ position: "absolute", left: "-2px", top: "1px", color: "#00ffa3", opacity: 0.7, clipPath: "inset(50% 0 10% 0)" }}>{children}</span>
        </>
      )}
    </span>
  );
}

function BarFill({ value, color, delay = 0, animated = true }) {
  const [width, setWidth] = useState(0);
  useEffect(() => {
    if (animated) {
      const t = setTimeout(() => setWidth(value), delay);
      return () => clearTimeout(t);
    } else {
      setWidth(value);
    }
  }, [value, delay, animated]);
  return (
    <div style={{ width: "100%", height: "8px", background: "#1a1a2e", borderRadius: "4px", overflow: "hidden" }}>
      <div style={{ width: `${width}%`, height: "100%", background: color, borderRadius: "4px", transition: animated ? "width 1.2s cubic-bezier(0.22, 1, 0.36, 1)" : "none" }} />
    </div>
  );
}

function ScoreRow({ label, selfScore, realScore, showReal, idx }) {
  return (
    <div style={{ marginBottom: "14px" }}>
      <div style={{ display: "flex", justifyContent: "space-between", marginBottom: "4px" }}>
        <span style={{ fontSize: "11px", textTransform: "uppercase", letterSpacing: "1.5px", color: "#8a8aaf" }}>{label}</span>
        <span style={{ fontSize: "12px", fontFamily: "'JetBrains Mono', monospace", color: showReal ? "#ff003c" : "#00ffa3" }}>
          {showReal ? `${selfScore}% → ${realScore}%` : `${selfScore}%`}
        </span>
      </div>
      <div style={{ position: "relative" }}>
        <BarFill value={selfScore} color={showReal ? "rgba(0,255,163,0.2)" : "#00ffa3"} delay={idx * 150} animated={!showReal} />
        {showReal && (
          <div style={{ position: "absolute", top: 0, left: 0, width: "100%", height: "100%" }}>
            <BarFill value={realScore} color="#ff003c" delay={idx * 200 + 300} animated />
          </div>
        )}
      </div>
    </div>
  );
}

function Scanline() {
  return (
    <div style={{ position: "absolute", top: 0, left: 0, right: 0, bottom: 0, pointerEvents: "none", background: "repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,255,163,0.015) 2px, rgba(0,255,163,0.015) 4px)", zIndex: 10 }} />
  );
}

export default function ConversatraitEmployerAd() {
  const [screen, setScreen] = useState(SCREENS.HOOK);
  const [candidateIdx, setCandidateIdx] = useState(0);
  const [picked, setPicked] = useState(null);
  const [showReal, setShowReal] = useState(false);
  const [fadeIn, setFadeIn] = useState(true);
  const [hookStep, setHookStep] = useState(0);
  const containerRef = useRef(null);

  const candidate = fakeCandidates[candidateIdx];

  useEffect(() => {
    setFadeIn(false);
    const t = setTimeout(() => setFadeIn(true), 50);
    return () => clearTimeout(t);
  }, [screen, showReal]);

  useEffect(() => {
    if (screen === SCREENS.HOOK) {
      const t1 = setTimeout(() => setHookStep(1), 800);
      const t2 = setTimeout(() => setHookStep(2), 2200);
      const t3 = setTimeout(() => setHookStep(3), 3400);
      return () => { clearTimeout(t1); clearTimeout(t2); clearTimeout(t3); };
    }
  }, [screen]);

  const transition = (next) => {
    setFadeIn(false);
    setTimeout(() => {
      setScreen(next);
      setFadeIn(true);
    }, 300);
  };

  const handlePick = (idx) => {
    setPicked(idx);
    setCandidateIdx(idx);
    setTimeout(() => {
      setShowReal(false);
      transition(SCREENS.REVEAL);
      setTimeout(() => setShowReal(true), 800);
    }, 600);
  };

  const styles = {
    wrapper: {
      width: "100%",
      maxWidth: "440px",
      margin: "0 auto",
      fontFamily: "'JetBrains Mono', 'SF Mono', 'Fira Code', monospace",
      color: "#e0e0f0",
      position: "relative",
      minHeight: "660px",
    },
    card: {
      background: "linear-gradient(165deg, #0a0a1a 0%, #0d0d24 50%, #0a0a1a 100%)",
      border: "1px solid rgba(0,255,163,0.15)",
      borderRadius: "12px",
      padding: "32px 28px",
      position: "relative",
      overflow: "hidden",
      boxShadow: "0 0 60px rgba(0,255,163,0.06), inset 0 1px 0 rgba(255,255,255,0.03)",
      opacity: fadeIn ? 1 : 0,
      transform: fadeIn ? "translateY(0)" : "translateY(8px)",
      transition: "opacity 0.4s ease, transform 0.4s ease",
    },
    neonGreen: { color: "#00ffa3" },
    neonRed: { color: "#ff003c" },
    dimText: { color: "#5a5a7a", fontSize: "11px", letterSpacing: "2px", textTransform: "uppercase" },
    headline: { fontSize: "26px", fontWeight: 800, lineHeight: 1.15, marginBottom: "16px", fontFamily: "'Space Grotesk', 'Inter', sans-serif", letterSpacing: "-0.5px" },
    subhead: { fontSize: "13px", color: "#8a8aaf", lineHeight: 1.6, marginBottom: "24px" },
    btn: {
      display: "inline-block",
      padding: "14px 28px",
      background: "transparent",
      border: "1px solid #00ffa3",
      color: "#00ffa3",
      fontFamily: "'JetBrains Mono', monospace",
      fontSize: "12px",
      letterSpacing: "2px",
      textTransform: "uppercase",
      cursor: "pointer",
      borderRadius: "6px",
      transition: "all 0.25s ease",
      textAlign: "center",
      width: "100%",
    },
    btnSolid: {
      display: "inline-block",
      padding: "14px 28px",
      background: "#00ffa3",
      border: "none",
      color: "#0a0a1a",
      fontFamily: "'JetBrains Mono', monospace",
      fontSize: "12px",
      fontWeight: 700,
      letterSpacing: "2px",
      textTransform: "uppercase",
      cursor: "pointer",
      borderRadius: "6px",
      transition: "all 0.25s ease",
      textAlign: "center",
      width: "100%",
    },
    tag: {
      display: "inline-block",
      padding: "4px 10px",
      background: "rgba(255,0,60,0.12)",
      border: "1px solid rgba(255,0,60,0.3)",
      borderRadius: "4px",
      fontSize: "10px",
      color: "#ff003c",
      letterSpacing: "1px",
      textTransform: "uppercase",
      marginBottom: "6px",
      marginRight: "6px",
    },
  };

  const renderHook = () => (
    <div style={styles.card}>
      <Scanline />
      <div style={{ ...styles.dimText, marginBottom: "24px" }}>
        <span style={{ color: "#00ffa3" }}>▌</span> conversatrait // hiring
      </div>

      <div style={{ minHeight: "220px" }}>
        <div style={{ opacity: hookStep >= 0 ? 1 : 0, transform: hookStep >= 0 ? "translateY(0)" : "translateY(12px)", transition: "all 0.6s ease" }}>
          <div style={{ ...styles.headline, color: "#e0e0f0" }}>
            Your last bad hire <GlitchText><span style={styles.neonRed}>looked perfect</span></GlitchText> on paper.
          </div>
        </div>

        <div style={{ opacity: hookStep >= 1 ? 1 : 0, transform: hookStep >= 1 ? "translateY(0)" : "translateY(12px)", transition: "all 0.6s ease" }}>
          <div style={{ ...styles.subhead, marginBottom: "8px" }}>
            They aced the personality assessment.<br />
            Crushed the interview.
          </div>
        </div>

        <div style={{ opacity: hookStep >= 2 ? 1 : 0, transform: hookStep >= 2 ? "translateY(0)" : "translateY(12px)", transition: "all 0.6s ease" }}>
          <div style={{ fontSize: "15px", color: "#ff003c", marginBottom: "28px", lineHeight: 1.5 }}>
            Then tanked the team in 90 days.
          </div>
        </div>

        <div style={{ opacity: hookStep >= 3 ? 1 : 0, transform: hookStep >= 3 ? "translateY(0)" : "translateY(12px)", transition: "all 0.6s ease" }}>
          <div style={{ fontSize: "12px", color: "#5a5a7a", marginBottom: "20px", lineHeight: 1.6 }}>
            Self-report assessments tell you who someone <em>wants</em> to be.<br />
            We show you who they <span style={styles.neonGreen}>actually are</span>.
          </div>
        </div>
      </div>

      <div style={{ opacity: hookStep >= 3 ? 1 : 0, transition: "opacity 0.6s ease" }}>
        <button
          style={styles.btn}
          onClick={() => transition(SCREENS.QUIZ)}
          onMouseEnter={(e) => { e.target.style.background = "rgba(0,255,163,0.1)"; e.target.style.boxShadow = "0 0 20px rgba(0,255,163,0.15)"; }}
          onMouseLeave={(e) => { e.target.style.background = "transparent"; e.target.style.boxShadow = "none"; }}
        >
          See the problem →
        </button>
      </div>

      <div style={{ position: "absolute", bottom: "-40px", right: "-40px", width: "140px", height: "140px", borderRadius: "50%", background: "radial-gradient(circle, rgba(0,255,163,0.06) 0%, transparent 70%)" }} />
    </div>
  );

  const renderQuiz = () => (
    <div style={styles.card}>
      <Scanline />
      <div style={{ ...styles.dimText, marginBottom: "20px" }}>
        <span style={{ color: "#00ffa3" }}>▌</span> scenario // two candidates
      </div>

      <div style={{ fontSize: "14px", color: "#c0c0d8", marginBottom: "24px", lineHeight: 1.6 }}>
        You're hiring for a team lead role. Both candidates took a standard personality assessment. Here are their scores:
      </div>

      {fakeCandidates.map((c, idx) => (
        <div
          key={idx}
          onClick={() => handlePick(idx)}
          style={{
            border: picked === idx ? "1px solid #00ffa3" : "1px solid rgba(255,255,255,0.06)",
            background: picked === idx ? "rgba(0,255,163,0.05)" : "rgba(255,255,255,0.02)",
            borderRadius: "8px",
            padding: "18px",
            marginBottom: "12px",
            cursor: "pointer",
            transition: "all 0.25s ease",
          }}
          onMouseEnter={(e) => { if (picked !== idx) e.currentTarget.style.borderColor = "rgba(0,255,163,0.4)"; }}
          onMouseLeave={(e) => { if (picked !== idx) e.currentTarget.style.borderColor = "rgba(255,255,255,0.06)"; }}
        >
          <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: "14px" }}>
            <span style={{ fontSize: "14px", fontWeight: 700, color: "#e0e0f0" }}>{c.name}</span>
            <span style={{ fontSize: "10px", color: "#00ffa3", letterSpacing: "1.5px", textTransform: "uppercase" }}>
              Avg: {Math.round((c.selfReport.teamwork + c.selfReport.leadership + c.selfReport.adaptability + c.selfReport.integrity) / 4)}%
            </span>
          </div>
          {Object.entries(c.selfReport).map(([key, val], i) => (
            <ScoreRow key={key} label={key} selfScore={val} realScore={c.reality[key]} showReal={false} idx={i} />
          ))}
        </div>
      ))}

      <div style={{ fontSize: "12px", color: "#5a5a7a", textAlign: "center", marginTop: "8px" }}>
        Tap a candidate to hire them
      </div>
    </div>
  );

  const renderReveal = () => (
    <div style={styles.card}>
      <Scanline />
      <div style={{ ...styles.dimText, marginBottom: "16px" }}>
        <span style={{ color: "#ff003c" }}>▌</span> reality check // {candidate.name.toLowerCase()}
      </div>

      <div style={{ fontSize: "18px", fontWeight: 800, color: "#ff003c", marginBottom: "6px", fontFamily: "'Space Grotesk', sans-serif" }}>
        Here's who you actually hired.
      </div>
      <div style={{ fontSize: "12px", color: "#5a5a7a", marginBottom: "20px" }}>
        <span style={{ color: "#00ffa3" }}>Green</span> = self-reported &nbsp; <span style={{ color: "#ff003c" }}>Red</span> = behavioral analysis
      </div>

      <div style={{ marginBottom: "20px" }}>
        {Object.entries(candidate.selfReport).map(([key, val], i) => (
          <ScoreRow key={key} label={key} selfScore={val} realScore={candidate.reality[key]} showReal={showReal} idx={i} />
        ))}
      </div>

      {showReal && (
        <div style={{ opacity: 1, transition: "opacity 0.5s ease" }}>
          <div style={{ ...styles.dimText, marginBottom: "10px", color: "#ff003c" }}>
            ⚠ red flags from actual conversations
          </div>
          <div style={{ background: "rgba(255,0,60,0.06)", border: "1px solid rgba(255,0,60,0.15)", borderRadius: "6px", padding: "14px", marginBottom: "16px" }}>
            {candidate.redFlags.map((f, i) => (
              <div key={i} style={{ fontSize: "12px", color: "#e0e0f0", marginBottom: i < candidate.redFlags.length - 1 ? "8px" : 0, paddingLeft: "14px", position: "relative" }}>
                <span style={{ position: "absolute", left: 0, color: "#ff003c" }}>×</span> {f}
              </div>
            ))}
          </div>

          <div style={{ ...styles.dimText, marginBottom: "8px", color: "#5a5a7a" }}>
            decoded from real messages
          </div>
          <div style={{ background: "rgba(0,255,163,0.03)", border: "1px solid rgba(0,255,163,0.08)", borderRadius: "6px", padding: "14px", marginBottom: "24px" }}>
            <pre style={{ fontSize: "11px", color: "#8a8aaf", whiteSpace: "pre-wrap", margin: 0, lineHeight: 1.7, fontFamily: "'JetBrains Mono', monospace" }}>
              {candidate.chatExcerpt}
            </pre>
          </div>

          <button
            style={styles.btnSolid}
            onClick={() => transition(SCREENS.PITCH)}
            onMouseEnter={(e) => { e.target.style.boxShadow = "0 0 24px rgba(0,255,163,0.3)"; }}
            onMouseLeave={(e) => { e.target.style.boxShadow = "none"; }}
          >
            Stop guessing →
          </button>
        </div>
      )}
    </div>
  );

  const renderPitch = () => (
    <div style={styles.card}>
      <Scanline />
      <div style={{ ...styles.dimText, marginBottom: "20px" }}>
        <span style={{ color: "#00ffa3" }}>▌</span> conversatrait // for hiring teams
      </div>

      <div style={{ ...styles.headline, color: "#e0e0f0", fontSize: "22px", marginBottom: "12px" }}>
        Hire who they <span style={styles.neonGreen}>are</span>.<br />
        Not who they <span style={{ color: "#5a5a7a", textDecoration: "line-through" }}>claim to be</span>.
      </div>

      <div style={{ fontSize: "13px", color: "#8a8aaf", lineHeight: 1.7, marginBottom: "28px" }}>
        ConversaTrait analyzes real workplace communication — Slack threads, emails, team chats — through 29+ behavioral frameworks. No self-report bias. No rehearsed answers.
      </div>

      <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: "10px", marginBottom: "28px" }}>
        {[
          ["⚡", "5-minute", "analysis"],
          ["🎯", "29+", "frameworks"],
          ["🧠", "Behavioral", "not self-report"],
          ["📊", "Dossier-style", "output"],
        ].map(([icon, line1, line2], i) => (
          <div key={i} style={{ background: "rgba(0,255,163,0.04)", border: "1px solid rgba(0,255,163,0.1)", borderRadius: "6px", padding: "14px 12px", textAlign: "center" }}>
            <div style={{ fontSize: "20px", marginBottom: "6px" }}>{icon}</div>
            <div style={{ fontSize: "13px", fontWeight: 700, color: "#e0e0f0" }}>{line1}</div>
            <div style={{ fontSize: "10px", color: "#5a5a7a", textTransform: "uppercase", letterSpacing: "1px" }}>{line2}</div>
          </div>
        ))}
      </div>

      <a
        href="https://conversatrait.com"
        target="_blank"
        rel="noopener noreferrer"
        style={{ ...styles.btnSolid, display: "block", textDecoration: "none" }}
        onMouseEnter={(e) => { e.target.style.boxShadow = "0 0 24px rgba(0,255,163,0.3)"; }}
        onMouseLeave={(e) => { e.target.style.boxShadow = "none"; }}
      >
        Try it free — 5 credits
      </a>

      <div style={{ textAlign: "center", marginTop: "14px" }}>
        <button
          onClick={() => { setHookStep(0); setPicked(null); setShowReal(false); transition(SCREENS.HOOK); setTimeout(() => setHookStep(0), 100); }}
          style={{ background: "none", border: "none", color: "#5a5a7a", fontSize: "11px", cursor: "pointer", letterSpacing: "1px", textTransform: "uppercase" }}
        >
          ↺ replay
        </button>
      </div>

      <div style={{ position: "absolute", top: "-30px", left: "-30px", width: "120px", height: "120px", borderRadius: "50%", background: "radial-gradient(circle, rgba(0,255,163,0.05) 0%, transparent 70%)" }} />
    </div>
  );

  return (
    <div style={{ padding: "20px 16px", minHeight: "100vh", background: "#06060f" }} ref={containerRef}>
      <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Space+Grotesk:wght@400;600;700;800&display=swap" rel="stylesheet" />
      <div style={styles.wrapper}>
        {screen === SCREENS.HOOK && renderHook()}
        {screen === SCREENS.QUIZ && renderQuiz()}
        {screen === SCREENS.REVEAL && renderReveal()}
        {screen === SCREENS.PITCH && renderPitch()}
      </div>
    </div>
  );
}
