## Hi there 👋

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
## 🏗️ Architettura del Sistema

### Schema Architetturale

```
┌─────────────────────────────────────────────────────────┐
│                    CLOUDFLARE CDN                       │
│              (SSL/TLS Termination)                      │
└───────────────┬─────────────────────┬───────────────────┘
                │                     │
    ┌───────────▼──────────┐  ┌───────▼────────────┐
    │   Frontend React     │  │   Backend API      │
    │   (Port 3000)        │  │   (Port 3002)      │
    │   - Nginx/Serve      │  │   - Express.js     │
    │   - Single Page App  │  │   - JWT Auth       │
    └──────────────────────┘  └─────────┬──────────┘
                                        │
                              ┌─────────▼──────────┐
                              │   MongoDB          │
                              │   (Port 27017)     │
                              │   - Membri         │
                              │   - Photos         │
                              │   - Users          │
                              └────────────────────┘
```

### Componenti Principali

1. **Frontend (React 19)**

   - Single Page Application (SPA)
   - Routing client-side con React Router
   - UI moderna con PrimeReact
   - Visualizzazione albero genealogico con family-chart

2. **Backend (Node.js/Express)**

   - API RESTful
   - Autenticazione JWT
   - Upload e gestione immagini
   - CRUD membri famiglia

3. **Database (MongoDB)**

   - Storage documenti membri
   - Metadata foto
   - Credenziali utenti

4. **Cloudflare Tunnel**
   - Esposizione sicura del servizio
   - SSL/TLS automatico
   - Protezione DDoS

---
