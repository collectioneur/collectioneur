
```aura width=860 height=200
<div style={{
  width: '100%',
  height: '100%',
  background: '#0c0c0f',
  display: 'flex',
  alignItems: 'center',
  fontFamily: 'Inter',
  position: 'relative',
  overflow: 'hidden',
  borderRadius: 16,
  border: '1px solid rgba(255,255,255,0.07)',
}}>
  <div style={{
    position: 'absolute',
    width: 560,
    height: 320,
    borderRadius: 280,
    background: 'radial-gradient(ellipse, rgba(80,30,220,0.65) 0%, rgba(50,20,160,0.3) 45%, transparent 70%)',
    bottom: -160,
    left: -60,
    display: 'flex',
  }} />
  <div style={{
    position: 'absolute',
    width: 420,
    height: 280,
    borderRadius: 210,
    background: 'radial-gradient(ellipse, rgba(30,60,255,0.45) 0%, transparent 70%)',
    bottom: -140,
    left: 140,
    display: 'flex',
  }} />
  <div style={{
    position: 'absolute',
    left: 48,
    top: 52,
    width: 96,
    height: 96,
    borderRadius: 48,
    background: 'linear-gradient(135deg, #6622ee, #2244ff)',
    display: 'flex',
    alignItems: 'center',
    justifyContent: 'center',
  }}>
    <img
      src={github.user.avatarUrl}
      width={88}
      height={88}
      style={{ borderRadius: 44 }}
    />
  </div>
  <div style={{
    display: 'flex',
    flexDirection: 'column',
    marginLeft: 168,
    gap: 8,
  }}>
    <div style={{
      display: 'flex',
      fontSize: 38,
      fontWeight: 800,
      color: '#ffffff',
      letterSpacing: '-1px',
      lineHeight: 1,
    }}>
      {github.user.name || github.user.login}
    </div>
    <div style={{
      display: 'flex',
      fontSize: 15,
      color: 'rgba(180,160,255,0.75)',
      fontWeight: 400,
      letterSpacing: '0.3px',
    }}>
      {github.user.bio || 'Full-Stack Engineer · Competitive Programmer · Open Source'}
    </div>
    <div style={{ display: 'flex', gap: 8, marginTop: 6 }}>
      {['React', 'TypeScript', 'Next.js', 'C++'].map(function(tag) {
        return (
          <div key={tag} style={{
            display: 'flex',
            padding: '4px 12px',
            borderRadius: 20,
            background: 'rgba(90,40,220,0.2)',
            border: '1px solid rgba(100,60,240,0.35)',
            color: 'rgba(200,190,255,0.85)',
            fontSize: 12,
            fontWeight: 600,
          }}>
            {tag}
          </div>
        );
      })}
    </div>
  </div>
</div>
```

<br>

```aura width=860 height=140
(function() {
  var stats = [
    { label: 'Repos', value: String(github.stats.totalRepos), color: '#a78bfa' },
    { label: 'Stars', value: String(github.stats.totalStars), color: '#60a5fa' },
    { label: 'Commits', value: String(github.stats.totalCommits), color: '#f59e0b' },
    { label: 'Forks', value: String(github.stats.totalForks), color: '#34d399' },
  ];

  return (
    <div style={{
      width: '100%',
      height: '100%',
      background: '#0c0c0f',
      display: 'flex',
      alignItems: 'center',
      justifyContent: 'center',
      fontFamily: 'Inter',
      borderRadius: 16,
      border: '1px solid rgba(255,255,255,0.07)',
      position: 'relative',
      overflow: 'hidden',
    }}>
      <div style={{
        position: 'absolute',
        width: 700,
        height: 260,
        borderRadius: 350,
        background: 'radial-gradient(ellipse, rgba(70,25,200,0.55) 0%, rgba(30,50,220,0.25) 45%, transparent 70%)',
        bottom: -160,
        left: '50%',
        marginLeft: -350,
        display: 'flex',
      }} />
      {stats.map(function(s, i) {
        return (
          <div key={s.label} style={{
            flexGrow: 1,
            display: 'flex',
            flexDirection: 'column',
            alignItems: 'center',
            justifyContent: 'center',
            padding: '16px 8px',
            borderRight: i < stats.length - 1 ? '1px solid rgba(255,255,255,0.06)' : 'none',
            gap: 5,
          }}>
            <div style={{
              display: 'flex',
              fontSize: 30,
              fontWeight: 800,
              color: s.color,
              lineHeight: 1,
            }}>
              {s.value}
            </div>
            <div style={{
              display: 'flex',
              fontSize: 11,
              color: 'rgba(200,195,220,0.45)',
              fontWeight: 600,
              letterSpacing: '1.5px',
            }}>
              {s.label.toUpperCase()}
            </div>
          </div>
        );
      })}
    </div>
  );
})()
```

<br>

```aura width=860 height=220
(function() {
  var topLangs = github.languages.slice(0, 6).map(function(l) { return l.name; });
  var categories = [
    { title: 'Languages', color: '#a78bfa', items: topLangs },
    { title: 'Frameworks', color: '#60a5fa', items: ['React', 'Next.js'] },
    { title: 'Databases', color: '#34d399', items: ['PostgreSQL', 'MySQL'] },
  ];

  return (
    <div style={{
      width: '100%',
      height: '100%',
      background: '#0c0c0f',
      display: 'flex',
      flexDirection: 'column',
      fontFamily: 'Inter',
      padding: '20px 32px',
      gap: 16,
      borderRadius: 16,
      border: '1px solid rgba(255,255,255,0.07)',
      position: 'relative',
      overflow: 'hidden',
    }}>
      <div style={{
        position: 'absolute',
        width: 500,
        height: 340,
        borderRadius: 250,
        background: 'radial-gradient(ellipse, rgba(70,25,200,0.5) 0%, rgba(30,50,220,0.2) 50%, transparent 70%)',
        bottom: -200,
        left: -80,
        display: 'flex',
      }} />
      <div style={{
        position: 'absolute',
        width: 380,
        height: 280,
        borderRadius: 190,
        background: 'radial-gradient(ellipse, rgba(30,60,255,0.35) 0%, transparent 70%)',
        bottom: -180,
        left: 160,
        display: 'flex',
      }} />
      <div style={{
        display: 'flex',
        fontSize: 10,
        fontWeight: 700,
        color: 'rgba(160,145,210,0.5)',
        letterSpacing: '3px',
      }}>
        TECH STACK
      </div>
      <div style={{ display: 'flex', flexDirection: 'column', gap: 14 }}>
        {categories.map(function(cat) {
          return (
            <div key={cat.title} style={{ display: 'flex', alignItems: 'center', gap: 16 }}>
              <div style={{
                display: 'flex',
                fontSize: 10,
                fontWeight: 700,
                color: cat.color,
                letterSpacing: '1px',
                width: 80,
                opacity: 0.85,
              }}>
                {cat.title.toUpperCase()}
              </div>
              <div style={{ display: 'flex', flexWrap: 'wrap', gap: 7 }}>
                {cat.items.map(function(item) {
                  return (
                    <div key={item} style={{
                      display: 'flex',
                      padding: '4px 13px',
                      borderRadius: 6,
                      background: cat.color + '15',
                      border: '1px solid ' + cat.color + '35',
                      color: 'rgba(225,220,255,0.85)',
                      fontSize: 12,
                      fontWeight: 600,
                    }}>
                      {item}
                    </div>
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
