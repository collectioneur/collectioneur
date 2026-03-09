
```aura width=860 height=200
<div style={{
  width: '100%',
  height: '100%',
  background: '#08080c',
  display: 'flex',
  alignItems: 'center',
  fontFamily: 'Inter',
  position: 'relative',
  overflow: 'hidden',
  borderRadius: 16,
  border: '1px solid rgba(110,80,220,0.18)',
}}>
  
  <div style={{
  width: '100%', height: '100%', background: '#08080c',
  display: 'flex', alignItems: 'center', fontFamily: 'Inter',
  position: 'relative', overflow: 'hidden', borderRadius: 16,
  border: '1px solid rgba(110,80,220,0.18)'
}}>

  <style>
    {`
      @keyframes float-slow {
        0%, 100% { transform: translateX(0px); opacity: 0.8; }
        50% { transform: translateX(35px); opacity: 1.2; }
      }
      @keyframes float-medium {
        0%, 100% { transform: translateX(0px); opacity: 0.7; }
        50% { transform: translateX(-25px); opacity: 1.1; }
      }
      @keyframes float-fast {
        0%, 100% { transform: translateX(0px); opacity: 0.9; }
        50% { transform: translateX(20px); opacity: 0.6; }
      }
      #glow-1 { animation: float-slow 8s ease-in-out infinite; }
      #glow-2 { animation: float-medium 12s ease-in-out infinite; }
      #glow-3 { animation: float-fast 9s ease-in-out infinite; }
      #glow-4 { animation: float-slow 11s ease-in-out infinite reverse; }
      #glow-5 { animation: float-medium 14s ease-in-out infinite reverse; }
    `}
  </style>

  <svg width="860" height="200" style={{ position: 'absolute', top: 0, left: 0 }}>
    <defs>
      <radialGradient id="g1" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stopColor="rgba(110,20,210,0.72)" />
        <stop offset="40%" stopColor="rgba(90,15,180,0.35)" />
        <stop offset="70%" stopColor="rgba(90,15,180,0)" />
      </radialGradient>
      <radialGradient id="g2" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stopColor="rgba(40,60,255,0.6)" />
        <stop offset="45%" stopColor="rgba(30,50,200,0.25)" />
        <stop offset="70%" stopColor="rgba(30,50,200,0)" />
      </radialGradient>
      <radialGradient id="g3" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stopColor="rgba(0,130,255,0.45)" />
        <stop offset="50%" stopColor="rgba(0,100,220,0.18)" />
        <stop offset="70%" stopColor="rgba(0,100,220,0)" />
      </radialGradient>
      <radialGradient id="g4" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stopColor="rgba(0,190,230,0.32)" />
        <stop offset="70%" stopColor="rgba(0,190,230,0)" />
      </radialGradient>
      <radialGradient id="g5" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stopColor="rgba(90,30,200,0.38)" />
        <stop offset="70%" stopColor="rgba(90,30,200,0)" />
      </radialGradient>
    </defs>

    <ellipse id="glow-1" cx="180" cy="230" rx="260" ry="190" fill="url(#g1)" />
    <ellipse id="glow-2" cx="300" cy="240" rx="220" ry="160" fill="url(#g2)" />
    <ellipse id="glow-3" cx="420" cy="240" rx="180" ry="140" fill="url(#g3)" />
    <ellipse id="glow-4" cx="550" cy="250" rx="150" ry="120" fill="url(#g4)" />
    <ellipse id="glow-5" cx="750" cy="250" rx="130" ry="110" fill="url(#g5)" />
  </svg>

  <div style={{
    position: 'absolute', left: 48, top: 52, width: 96, height: 96,
    borderRadius: 48, background: 'linear-gradient(135deg, #6622ee, #0088ff)',
    display: 'flex', alignItems: 'center', justifyContent: 'center',
  }}>
    <img src={github.user.avatarUrl} width={88} height={88} style={{ borderRadius: 44 }} />
  </div>
  
  <div style={{ display:'flex', flexDirection:'column', marginLeft:168, gap:8, zIndex: 10 }}>
    <div style={{ display:'flex', fontSize:38, fontWeight:800, color:'#ffffff', letterSpacing:'-1px', lineHeight:1 }}>
      {github.user.name || github.user.login}
    </div>
    <div style={{ display:'flex', fontSize:15, color:'rgba(180,165,255,0.8)', fontWeight:400, letterSpacing:'0.3px' }}>
      {github.user.bio || 'Full-Stack Engineer · Competitive Programmer · Open Source'}
    </div>
    <div style={{ display:'flex', gap:8, marginTop:6 }}>
      {['React', 'TypeScript', 'Next.js', 'C++'].map(function(tag) {
        return (
          <div key={tag} style={{
            display:'flex', padding:'4px 12px', borderRadius:20,
            background:'rgba(80,40,220,0.18)', border:'1px solid rgba(100,70,240,0.32)',
            color:'rgba(205,195,255,0.85)', fontSize:12, fontWeight:600,
          }}>{tag}</div>
        );
      })}
    </div>
  </div>
</div>
```

```aura width=860 height=140
(function() {
  var stats = [
    { label: 'Repos', value: String(github.stats.totalRepos), color: '#a78bfa' },
    { label: 'Stars', value: String(github.stats.totalStars), color: '#60a5fa' },
    { label: 'Commits', value: String(github.stats.totalCommits), color: '#f59e0b' },
  ];

  return (
    <div style={{
      width: '100%', height: '100%',
      background: '#08080c',
      display: 'flex', alignItems: 'center', justifyContent: 'center',
      fontFamily: 'Inter', borderRadius: 16,
      border: '1px solid rgba(110,80,220,0.18)',
      position: 'relative', overflow: 'hidden',
    }}>
      {/* violet left */}
      <div style={{ position:'absolute', width:420, height:300, borderRadius:210, background:'radial-gradient(ellipse, rgba(110,20,210,0.65) 0%, rgba(80,15,170,0.28) 45%, transparent 70%)', bottom:-190, right:-60, display:'flex' }} />
      {/* blue center-left */}
      <div style={{ position:'absolute', width:380, height:280, borderRadius:190, background:'radial-gradient(ellipse, rgba(40,70,255,0.55) 0%, rgba(20,50,200,0.22) 45%, transparent 70%)', bottom:-180, right:120, display:'flex' }} />
      {/* cyan-blue center */}
      <div style={{ position:'absolute', width:340, height:260, borderRadius:170, background:'radial-gradient(ellipse, rgba(0,140,255,0.42) 0%, transparent 70%)', bottom:-170, right:290, display:'flex' }} />
      {/* cyan right */}
      <div style={{ position:'absolute', width:300, height:240, borderRadius:150, background:'radial-gradient(ellipse, rgba(0,195,235,0.3) 0%, transparent 70%)', bottom:-170, right:460, display:'flex' }} />
      {/* violet far-right */}
      <div style={{ position:'absolute', width:260, height:220, borderRadius:130, background:'radial-gradient(ellipse, rgba(100,30,210,0.4) 0%, transparent 70%)', bottom:-160, left:-30, display:'flex' }} />
      {stats.map(function(s, i) {
        return (
          <div key={s.label} style={{
            flexGrow: 1, display: 'flex', flexDirection: 'column',
            alignItems: 'center', justifyContent: 'center',
            padding: '16px 8px',
            borderRight: i < stats.length - 1 ? '1px solid rgba(255,255,255,0.06)' : 'none',
            gap: 5,
          }}>
            <div style={{ display:'flex', fontSize:30, fontWeight:800, color:s.color, lineHeight:1 }}>
              {s.value}
            </div>
            <div style={{ display:'flex', fontSize:11, color:'rgba(200,195,225,0.45)', fontWeight:600, letterSpacing:'1.5px' }}>
              {s.label.toUpperCase()}
            </div>
          </div>
        );
      })}
    </div>
  );
})()
```

```aura width=860 height=168
(function() {
  var topLangs = github.languages.slice(0, 6).map(function(l) { return l.name; });
  var categories = [
    { title: 'Languages', color: '#a78bfa', items: topLangs },
    { title: 'Frameworks', color: '#60a5fa', items: ['React Native', 'React', 'Next.js'] },
  ];

  return (
    <div style={{
      width: '100%', height: '100%',
      background: '#08080c',
      display: 'flex', flexDirection: 'column',
      fontFamily: 'Inter', padding: '18px 32px', gap: 14,
      borderRadius: 16, border: '1px solid rgba(110,80,220,0.18)',
      position: 'relative', overflow: 'hidden',
    }}>
      {/* violet — far left */}
      <div style={{ position:'absolute', width:520, height:340, borderRadius:260, background:'radial-gradient(ellipse, rgba(115,20,215,0.68) 0%, rgba(85,15,175,0.3) 42%, transparent 70%)', bottom:-170, left:-90, display:'flex' }} />
      {/* blue-violet */}
      <div style={{ position:'absolute', width:440, height:280, borderRadius:220, background:'radial-gradient(ellipse, rgba(55,55,255,0.55) 0%, rgba(35,45,210,0.22) 45%, transparent 70%)', bottom:-150, left:100, display:'flex' }} />
      {/* cyan-blue center */}
      <div style={{ position:'absolute', width:380, height:260, borderRadius:190, background:'radial-gradient(ellipse, rgba(0,130,255,0.42) 0%, rgba(0,100,220,0.16) 50%, transparent 70%)', bottom:-140, left:270, display:'flex' }} />
      {/* cyan */}
      <div style={{ position:'absolute', width:320, height:220, borderRadius:160, background:'radial-gradient(ellipse, rgba(0,185,240,0.32) 0%, transparent 70%)', bottom:-130, left:430, display:'flex' }} />
      {/* violet right edge */}
      <div style={{ position:'absolute', width:280, height:200, borderRadius:140, background:'radial-gradient(ellipse, rgba(100,25,205,0.42) 0%, transparent 70%)', bottom:-120, right:-30, display:'flex' }} />
      {/* hot center highlight */}
      <div style={{ position:'absolute', width:200, height:160, borderRadius:100, background:'radial-gradient(ellipse, rgba(60,80,255,0.35) 0%, transparent 70%)', bottom:-50, left:320, display:'flex' }} />
      <div style={{ display:'flex', fontSize:10, fontWeight:700, color:'rgba(155,140,210,0.5)', letterSpacing:'3px' }}>
        TECH STACK
      </div>
      <div style={{ display:'flex', flexDirection:'column', gap:14 }}>
        {categories.map(function(cat) {
          return (
            <div key={cat.title} style={{ display:'flex', alignItems:'center', gap:16 }}>
              <div style={{ display:'flex', fontSize:10, fontWeight:700, color:cat.color, letterSpacing:'1px', width:80 }}>
                {cat.title.toUpperCase()}
              </div>
              <div style={{ display:'flex', flexWrap:'wrap', gap:7 }}>
                {cat.items.map(function(item) {
                  return (
                    <div key={item} style={{
                      display:'flex', padding:'4px 13px', borderRadius:6,
                      background:cat.color + '15', border:'1px solid ' + cat.color + '35',
                      color:'rgba(225,220,255,0.85)', fontSize:12, fontWeight:600,
                    }}>{item}</div>
                  );
                })}
              </div>
            </div>
          );
        })}
      </div>
    </div>
  );
})()
```
