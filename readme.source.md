```aura
// meta: width=860, height=200
export default function Hero() {
  return (
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
    }}>
      {/* Ambient glow blobs */}
      <div style={{
        position: 'absolute',
        width: 320,
        height: 320,
        borderRadius: '50%',
        background: 'radial-gradient(circle, rgba(120,80,255,0.35) 0%, transparent 70%)',
        top: -80,
        left: -40,
      }} />
      <div style={{
        position: 'absolute',
        width: 260,
        height: 260,
        borderRadius: '50%',
        background: 'radial-gradient(circle, rgba(0,200,255,0.25) 0%, transparent 70%)',
        bottom: -60,
        right: 60,
      }} />

      {/* Avatar ring */}
      <div style={{
        position: 'absolute',
        left: 48,
        top: '50%',
        transform: 'translateY(-50%)',
        width: 96,
        height: 96,
        borderRadius: '50%',
        background: 'linear-gradient(135deg, #7b2ff7, #00c8ff)',
        display: 'flex',
        alignItems: 'center',
        justifyContent: 'center',
        boxShadow: '0 0 32px rgba(123,47,247,0.6)',
      }}>
        <div style={{
          width: 88,
          height: 88,
          borderRadius: '50%',
          background: '#1a1a2e',
          display: 'flex',
          alignItems: 'center',
          justifyContent: 'center',
          fontSize: 36,
        }}>
          {'Y'}
        </div>
      </div>

      {/* Text block */}
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
          fontSize: 16,
          color: 'rgba(180,160,255,0.9)',
          fontWeight: 400,
          letterSpacing: '0.5px',
        }}>
          Full-Stack Engineer · Competitive Programmer · Open Source Enthusiast
        </div>
        <div style={{
          display: 'flex',
          gap: 12,
          marginTop: 4,
        }}>
          {['React', 'TypeScript', 'Next.js', 'C++'].map((tag) => (
            <div key={tag} style={{
              padding: '4px 12px',
              borderRadius: 20,
              background: 'rgba(123,47,247,0.25)',
              border: '1px solid rgba(123,47,247,0.5)',
              color: '#c4b5fd',
              fontSize: 12,
              fontWeight: 600,
              letterSpacing: '0.3px',
            }}>
              {tag}
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}
```

<br>

```aura
// meta: width=860, height=140
export default function Stats() {
  const stats = [
    { label: 'Repos', value: '30+', icon: '📦', color: '#7b2ff7' },
    { label: 'LeetCode', value: '200+', icon: '🧩', color: '#00c8ff' },
    { label: 'Codeforces', value: 'Pupil', icon: '⚡', color: '#f59e0b' },
    { label: 'Experience', value: '3 yrs', icon: '🚀', color: '#10b981' },
  ];

  return (
    <div style={{
      width: '100%',
      height: '100%',
      background: 'linear-gradient(135deg, #0f0c29 0%, #1a1a2e 100%)',
      display: 'flex',
      alignItems: 'center',
      justifyContent: 'center',
      gap: 0,
      fontFamily: 'Inter',
      padding: '0 24px',
    }}>
      {stats.map((s, i) => (
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
          <div style={{ fontSize: 28 }}>{s.icon}</div>
          <div style={{
            fontSize: 28,
            fontWeight: 800,
            color: s.color,
            lineHeight: 1,
            textShadow: `0 0 20px ${s.color}80`,
          }}>
            {s.value}
          </div>
          <div style={{
            fontSize: 12,
            color: 'rgba(200,200,220,0.6)',
            fontWeight: 500,
            textTransform: 'uppercase',
            letterSpacing: '1px',
          }}>
            {s.label}
          </div>
        </div>
      ))}
    </div>
  );
}
```

<br>

```aura
// meta: width=860, height=220
export default function TechStack() {
  const categories = [
    {
      title: 'Languages',
      color: '#7b2ff7',
      items: ['TypeScript', 'JavaScript', 'C++', 'C', 'HTML5', 'CSS3'],
    },
    {
      title: 'Frameworks',
      color: '#00c8ff',
      items: ['React', 'Next.js'],
    },
    {
      title: 'Databases',
      color: '#10b981',
      items: ['PostgreSQL', 'MySQL'],
    },
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
    }}>
      <div style={{
        fontSize: 13,
        fontWeight: 700,
        color: 'rgba(180,160,255,0.7)',
        letterSpacing: '2px',
        textTransform: 'uppercase',
      }}>
        Tech Stack
      </div>

      <div style={{ display: 'flex', flexDirection: 'column', gap: 14 }}>
        {categories.map((cat) => (
          <div key={cat.title} style={{ display: 'flex', alignItems: 'center', gap: 16 }}>
            <div style={{
              fontSize: 11,
              fontWeight: 700,
              color: cat.color,
              textTransform: 'uppercase',
              letterSpacing: '1px',
              width: 80,
              flexShrink: 0,
            }}>
              {cat.title}
            </div>
            <div style={{ display: 'flex', flexWrap: 'wrap', gap: 8 }}>
              {cat.items.map((item) => (
                <div key={item} style={{
                  padding: '5px 14px',
                  borderRadius: 6,
                  background: `${cat.color}18`,
                  border: `1px solid ${cat.color}40`,
                  color: '#e2e0ff',
                  fontSize: 13,
                  fontWeight: 600,
                }}>
                  {item}
                </div>
              ))}
            </div>
          </div>
        ))}
      </div>
    </div>
  );
}
```

<br>

```aura
// meta: width=860, height=100
export default function Footer() {
  const links = [
    { label: 'Facebook', icon: '🌐', url: 'https://www.facebook.com/profile.php?id=100095076236650' },
    { label: 'Codeforces', icon: '⚡', url: 'https://codeforces.com/profile/yyourharr' },
    { label: 'LeetCode', icon: '🧩', url: 'https://leetcode.com/yehorkharchenko/' },
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
    }}>
      {links.map((link) => (
        <div key={link.label} style={{
          display: 'flex',
          alignItems: 'center',
          gap: 8,
          padding: '10px 20px',
          borderRadius: 8,
          background: 'rgba(255,255,255,0.05)',
          border: '1px solid rgba(255,255,255,0.1)',
        }}>
          <span style={{ fontSize: 18 }}>{link.icon}</span>
          <span style={{ color: '#c4b5fd', fontSize: 14, fontWeight: 600 }}>{link.label}</span>
        </div>
      ))}
      <div style={{
        position: 'absolute',
        right: 32,
        fontSize: 11,
        color: 'rgba(255,255,255,0.2)',
        fontFamily: 'Inter',
      }}>
        generated by readme-aura
      </div>
    </div>
  );
}
```
