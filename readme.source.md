# Yehor Kharchenko

```aura width=860 height=200
<div style={{
  width: '100%',
  height: '100%',
  background: 'linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%)',
  display: 'flex',
  flexDirection: 'column',
  alignItems: 'center',
  justifyContent: 'center',
  fontFamily: 'Inter',
  position: 'relative',
  overflow: 'hidden',
  borderRadius: 15,
}}>
  <div style={{
    position: 'absolute',
    width: 320,
    height: 320,
    borderRadius: 160,
    background: 'radial-gradient(circle, rgba(120,80,255,0.35) 0%, transparent 70%)',
    top: -80,
    left: -40,
    display: 'flex',
  }} />
  <div style={{
    position: 'absolute',
    width: 260,
    height: 260,
    borderRadius: 130,
    background: 'radial-gradient(circle, rgba(0,200,255,0.25) 0%, transparent 70%)',
    bottom: -60,
    right: 60,
    display: 'flex',
  }} />
  <div style={{
    position: 'absolute',
    left: 48,
    top: 52,
    width: 96,
    height: 96,
    borderRadius: 48,
    background: 'linear-gradient(135deg, #7b2ff7, #00c8ff)',
    display: 'flex',
    alignItems: 'center',
    justifyContent: 'center',
  }}>
    <div style={{
      width: 88,
      height: 88,
      borderRadius: 44,
      background: '#1a1a2e',
      display: 'flex',
      alignItems: 'center',
      justifyContent: 'center',
      fontSize: 36,
      color: '#ffffff',
    }}>
      Y
    </div>
  </div>
  <div style={{
    display: 'flex',
    flexDirection: 'column',
    marginLeft: 168,
    gap: 8,
  }}>
    <div style={{
      fontSize: 38,
      fontWeight: 800,
      color: '#ffffff',
      letterSpacing: '-1px',
      lineHeight: 1,
    }}>
      Yehor Kharchenko
    </div>
    <div style={{
      fontSize: 15,
      color: 'rgba(180,160,255,0.9)',
      fontWeight: 400,
      letterSpacing: '0.5px',
    }}>
      Full-Stack Engineer · Competitive Programmer · Open Source
    </div>
    <div style={{ display: 'flex', gap: 10, marginTop: 6 }}>
      {['React', 'TypeScript', 'Next.js', 'C++'].map(function(tag) {
        return (
          <div key={tag} style={{
            padding: '4px 12px',
            borderRadius: 20,
            background: 'rgba(123,47,247,0.25)',
            border: '1px solid rgba(123,47,247,0.5)',
            color: '#c4b5fd',
            fontSize: 12,
            fontWeight: 600,
            display: 'flex',
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
    { label: 'Repos', value: '21', color: '#7b2ff7' },
    { label: 'LeetCode', value: '200+', color: '#00c8ff' },
    { label: 'Codeforces', value: 'Pupil', color: '#f59e0b' },
    { label: 'Languages', value: '5', color: '#10b981' },
  ];

  return (
    <div style={{
      width: '100%',
      height: '100%',
      background: 'linear-gradient(135deg, #0f0c29 0%, #1a1a2e 100%)',
      display: 'flex',
      alignItems: 'center',
      justifyContent: 'center',
      fontFamily: 'Inter',
      borderRadius: 15,
    }}>
      {stats.map(function(s, i) {
        return (
          <div key={s.label} style={{
            flex: 1,
            display: 'flex',
            flexDirection: 'column',
            alignItems: 'center',
            justifyContent: 'center',
            padding: '16px 8px',
            borderRight: i < stats.length - 1 ? '1px solid rgba(255,255,255,0.08)' : 'none',
            gap: 6,
          }}>
            <div style={{
              fontSize: 30,
              fontWeight: 800,
              color: s.color,
              lineHeight: 1,
            }}>
              {s.value}
            </div>
            <div style={{
              fontSize: 11,
              color: 'rgba(200,200,220,0.6)',
              fontWeight: 600,
              letterSpacing: '1.5px',
            }}>
              {s.label}
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
  var categories = [
    { title: 'Languages', color: '#7b2ff7', items: ['TypeScript', 'JavaScript', 'C++', 'C', 'HTML5', 'CSS3'] },
    { title: 'Frameworks', color: '#00c8ff', items: ['React', 'Next.js'] },
    { title: 'Databases', color: '#10b981', items: ['PostgreSQL', 'MySQL'] },
  ];

  return (
    <div style={{
      width: '100%',
      height: '100%',
      background: 'linear-gradient(135deg, #0f0c29 0%, #1a1a2e 100%)',
      display: 'flex',
      flexDirection: 'column',
      fontFamily: 'Inter',
      padding: '20px 32px',
      gap: 16,
      borderRadius: 15,
    }}>
      <div style={{
        fontSize: 11,
        fontWeight: 700,
        color: 'rgba(180,160,255,0.6)',
        letterSpacing: '2.5px',
      }}>
        TECH STACK
      </div>
      <div style={{ display: 'flex', flexDirection: 'column', gap: 16 }}>
        {categories.map(function(cat) {
          return (
            <div key={cat.title} style={{ display: 'flex', alignItems: 'center', gap: 16 }}>
              <div style={{
                fontSize: 11,
                fontWeight: 700,
                color: cat.color,
                letterSpacing: '1px',
                width: 80,
              }}>
                {cat.title.toUpperCase()}
              </div>
              <div style={{ display: 'flex', flexWrap: 'wrap', gap: 8 }}>
                {cat.items.map(function(item) {
                  return (
                    <div key={item} style={{
                      padding: '5px 14px',
                      borderRadius: 6,
                      background: cat.color + '18',
                      border: '1px solid ' + cat.color + '40',
                      color: '#e2e0ff',
                      fontSize: 13,
                      fontWeight: 600,
                      display: 'flex',
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

<br>

```aura width=860 height=100
(function() {
  var links = [
    { label: 'Facebook', icon: '🌐' },
    { label: 'Codeforces', icon: '⚡' },
    { label: 'LeetCode', icon: '🧩' },
  ];

  return (
    <div style={{
      width: '100%',
      height: '100%',
      background: 'linear-gradient(135deg, #0f0c29 0%, #302b63 100%)',
      display: 'flex',
      alignItems: 'center',
      justifyContent: 'center',
      gap: 32,
      fontFamily: 'Inter',
      borderRadius: 15,
    }}>
      {links.map(function(link) {
        return (
          <div key={link.label} style={{
            display: 'flex',
            alignItems: 'center',
            gap: 8,
            padding: '10px 22px',
            borderRadius: 8,
            background: 'rgba(255,255,255,0.05)',
            border: '1px solid rgba(255,255,255,0.1)',
          }}>
            <span style={{ fontSize: 18 }}>{link.icon}</span>
            <span style={{ color: '#c4b5fd', fontSize: 14, fontWeight: 600 }}>{link.label}</span>
          </div>
        );
      })}
    </div>
  );
})()
```
