# Mobile Block Screen — Spec & Code

## Overview
Shown instead of the main app when `window.innerWidth < 768`.

---

## Design Specs

### Layout
- Full-height column flex (`min-height: 100vh`)
- Background: `#ffffff`
- Font: `system-ui, sans-serif`

### 1. Header
- Padding: `14px 20px`
- Border-bottom: `1px solid #e5e7eb`
- Content: Metzler logo (SVG, height `26px`)

### 2. Hero Image
- Width: `100%`, Height: `220px`
- `object-fit: cover`, `object-position: center`
- Source: `/image621.png`

### 3. Content Area
- Padding: `28px 24px`
- Flex column, `flex: 1`

**Heading**
- Text: Gestalten Sie Ihre Briefkastenanlage individuell nach Ihren Wünschen!
- Size: `22px`, Weight: `700`, Color: `#1a1a1a`
- Line-height: `1.3`, Margin-bottom: `16px`

**Info container**
- Border-radius: `10px`
- Border: `1px solid #e5e7eb`
- Background: `#f9fafb`
- Padding: `16px 18px`

  - Bold title: Konfigurator für Briefkastenanlagen – optimiert für Desktop und Laptop
    - `display: block`, `margin-bottom: 6px`, Color: `#1a1a1a`
  - Body text: Der Konfigurator für Briefkastenanlagen ist ausschließlich auf Desktop-Computern und Laptops optimiert. Eine Nutzung auf mobilen Geräten ist leider nicht möglich.
    - Size: `14px`, Color: `#374151`, Line-height: `1.7`

---

## Code

### Trigger
```jsx
if (window.innerWidth < 768) return <MobileBlock />;
```

### Component
```jsx
function MobileBlock() {
  return (
    <div style={{ minHeight: "100vh", display: "flex", flexDirection: "column", fontFamily: "system-ui, sans-serif", background: "#fff" }}>

      {/* Header */}
      <div style={{ padding: "14px 20px", borderBottom: "1px solid #e5e7eb", display: "flex", alignItems: "center" }}>
        <svg height="26" viewBox="0 0 180 40" fill="none">
          <rect x="0" y="0" width="36" height="36" rx="3" fill="#c0392b" />
          <text x="18" y="26" textAnchor="middle" fill="white" fontSize="22" fontWeight="900" fontFamily="system-ui, sans-serif">M</text>
          <text x="46" y="27" fill="#1a1a1a" fontSize="22" fontWeight="700" fontFamily="system-ui, sans-serif" letterSpacing="-0.5">METZLER</text>
        </svg>
      </div>

      {/* Hero Image */}
      <div style={{ width: "100%", height: 220, overflow: "hidden" }}>
        <img
          src="/image621.png"
          alt="Briefkastenanlage"
          style={{ width: "100%", height: "100%", objectFit: "cover", objectPosition: "center" }}
        />
      </div>

      {/* Content */}
      <div style={{ padding: "28px 24px", flex: 1, display: "flex", flexDirection: "column" }}>

        {/* Heading */}
        <div style={{ fontSize: 22, fontWeight: 700, color: "#1a1a1a", lineHeight: 1.3, marginBottom: 16 }}>
          Gestalten Sie Ihre Briefkastenanlage individuell nach Ihren Wünschen!
        </div>

        {/* Info container */}
        <div style={{ borderRadius: 10, border: "1px solid #e5e7eb", background: "#f9fafb", padding: "16px 18px", fontSize: 14, color: "#374151", lineHeight: 1.7 }}>
          <strong style={{ display: "block", marginBottom: 6, color: "#1a1a1a" }}>
            Konfigurator für Briefkastenanlagen – optimiert für Desktop und Laptop
          </strong>
          Der Konfigurator für Briefkastenanlagen ist ausschließlich auf Desktop-Computern und Laptops optimiert. Eine Nutzung auf mobilen Geräten ist leider nicht möglich.
        </div>

      </div>
    </div>
  );
}
```

### Required asset
- File: `/public/image621.png`
- Hero photo of the Briefkastenanlage installation
