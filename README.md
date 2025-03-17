# text-templates-app
import React, { useState } from "react";
import CopyCard from "./components/CopyCard";

function App() {
  // State für Namen
  const [firstName, setFirstName] = useState("");
  const [surname, setSurname] = useState("");

  // Aktuelles Datum + Uhrzeit
  const dateTime = new Date().toLocaleString();

  return (
    <div style={{ padding: "20px", fontFamily: "Arial, sans-serif" }}>
      <h1>Textvorlagen - First Level Retention</h1>

      {/* Eingabefelder */}
      <label>Vorname: </label>
      <input
        type="text"
        value={firstName}
        onChange={(e) => setFirstName(e.target.value)}
        placeholder="Vorname eingeben"
        style={{ marginRight: "10px" }}
      />

      <label>Nachname: </label>
      <input
        type="text"
        value={surname}
        onChange={(e) => setSurname(e.target.value)}
        placeholder="Nachname eingeben"
      />

      {/* Textbausteine */}
      <div style={{ display: "flex", flexWrap: "wrap", marginTop: "20px" }}>
        <CopyCard title="Nur dein Name und Datum + Uhrzeit">
          {firstName} {surname} {dateTime}
        </CopyCard>

        <CopyCard title="Nicht erreicht">
          {firstName} {surname} {dateTime} ❌ Nicht erreicht
        </CopyCard>

        <CopyCard title="MVT Retention: Kunde nicht erreicht">
          ⭐ MVT Retention Manager: {firstName} {surname}_MVT_NE_{dateTime}
        </CopyCard>

        <CopyCard title="MVT Retention: neuer MVT vereinbart">
          ⭐ MVT Retention Manager: {firstName} {surname}_NEU_MVT_{dateTime}
        </CopyCard>
      </div>
    </div>
  );
}

export default App;
