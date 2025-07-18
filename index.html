# avitrix-predictor-
Aviatrix Predictor Pro Web App
<!DOCTYPE html><html>
<head>
  <title>Aviatrix Predictor Pro</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #1e1e1e;
      color: #fff;
      padding: 20px;
      max-width: 900px;
      margin: auto;
    }
    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      background: #2c2c2c;
      color: white;
      border: 1px solid #444;
      border-radius: 6px;
    }
    button:hover {
      background: #3a3a3a;
    }
    .result, .chart-box, .config, .analytics {
      background: #2c2c2c;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 0 5px #111;
      margin-top: 20px;
    }
    .export {
      margin-top: 10px;
      display: flex;
      gap: 10px;
      justify-content: space-between;
    }
    canvas {
      background: #fff;
    }
  </style>
</head>
<body>
  <h2>🎯 Aviatrix Predictor Pro</h2><label>💰 Balance:</label> <input type="number" id="balance" placeholder="e.g. 100">

<label>📉 Latest Crash Multiplier:</label> <input type="number" id="newCrash" step="0.01" placeholder="e.g. 1.30">

<label>📈 Streak Type:</label> <select id="streakType"> <option value="win">Win</option> <option value="loss">Loss</option> </select>

<label>🔁 Streak Count:</label> <input type="number" id="streakCount" placeholder="e.g. 3">

  <div class="config">
    <h4>🎛 Strategy Settings</h4>
    <label>Risk Level:</label>
    <select id="riskLevel">
      <option value="safe">Safe</option>
      <option value="medium" selected>Medium</option>
      <option value="risky">Risky</option>
    </select><label>Cashout Target:</label>
<select id="cashoutPref">
  <option value="1.5">1.50x</option>
  <option value="1.8" selected>1.80x</option>
  <option value="2">2.00x</option>
  <option value="2.5">2.50x</option>
  <option value="5">5.00x</option>
</select>

  </div><button onclick="predict()">🔍 Analyze</button>

  <div class="export">
    <button onclick="exportHistory()">⬇ Export</button>
    <button onclick="clearHistory()">🧹 Clear</button>
  </div>  <div class="result" id="output"></div>
  <div class="analytics" id="extraStats"></div>
  <div class="chart-box">
    <canvas id="historyChart" height="150"></canvas>
  </div>  <script>
    let history = JSON.parse(localStorage.getItem("aviatrix_history") || "[]");

    function updateHistory(val) {
      if (!isNaN(val)) {
        history.push(val);
        if (history.length > 30) history = history.slice(-30);
        localStorage.setItem("aviatrix_history", JSON.stringify(history));
      }
    }

    function smartBet(balance, risk) {
      if (risk === "safe") return balance * 0.02;
      if (risk === "medium") return balance * 0.05;
      return balance * 0.10;
    }

    function analyzeMarket(history) {
      const low = history.slice(-10).filter(v => v < 1.5).length;
      const high = history.slice(-10).filter(v => v > 10).length;
      const streakLow = history.slice(-5).every(v => v < 2.0);

      if (streakLow) return ["🔥 Low streak! High spike incoming?", "2.50x–5.00x"];
      if (high > 0) return ["❌ Market cooled off. Be cautious.", "1.30x–1.60x"];
      if (low >= 7) return ["⚠️ Volatility high.", "1.40x–1.60x"];
      return ["✅ Normal conditions.", "1.80x–2.00x"];
    }

    function detectPattern(history) {
      const last = history.slice(-3);
      if (last.length < 3) return "🟡 Not enough data.";
      if (last[0] < 1.5 && last[1] < 1.5 && last[2] >= 2.5) return "🔁 Spike after low crash!";
      if (last[0] > 2 && last[1] < 2 && last[2] > 2) return "📉 Alternating win-loss detected.";
      if (last.every((v, i, arr) => i === 0 || v > arr[i - 1])) return "📈 Trend rising.";
      return "🟢 No strong pattern.";
    }

    function predictMultiplier(history) {
      const avg = history.reduce((a, b) => a + b, 0) / history.length;
      let next = avg * 0.92 + (Math.random() * 0.5);
      return next.toFixed(2);
    }

    function confidenceScore(next) {
      if (next > 2.5) return "🔺 High confidence for spike";
      if (next > 1.8) return "🟢 Good chance for win";
      return "🔻 Low confidence";
    }

    function predict() {
      const newCrash = parseFloat(document.getElementById("newCrash").value);
      const balance = parseFloat(document.getElementById("balance").value);
      const streakCount = parseInt(document.getElementById("streakCount").value);
      const risk = document.getElementById("riskLevel").value;
      const cashoutPref = document.getElementById("cashoutPref").value;

      if (isNaN(newCrash) || isNaN(balance) || isNaN(streakCount)) {
        document.getElementById("output").innerHTML = "❌ Please fill all fields correctly.";
        return;
      }

      updateHistory(newCrash);

      const [marketTip, cashoutRange] = analyzeMarket(history);
      const pattern = detectPattern(history);
      const suggestedBet = smartBet(balance, risk).toFixed(2);
      const prediction = predictMultiplier(history);
      const confidence = confidenceScore(prediction);

      document.getElementById("output").innerHTML = `
        <b>🧠 Market Tip:</b> ${marketTip}<br>
        <b>🔍 Pattern:</b> ${pattern}<br>
        <b>🎯 Target Cashout:</b> ${cashoutPref}x (Suggested: ${cashoutRange})<br>
        <b>💸 Bet Suggestion:</b> R${suggestedBet}<br>
        <b>🔮 Predicted Multiplier:</b> ${prediction}x<br>
        <b>🧪 Confidence:</b> ${confidence}
      `;

      const wins = history.filter(x => x >= parseFloat(cashoutPref)).length;
      const avgMulti = history.reduce((a, b) => a + b, 0) / history.length;
      const winRate = ((wins / history.length) * 100).toFixed(1);

      document.getElementById("extraStats").innerHTML = `
        <b>📊 Total Rounds:</b> ${history.length}<br>
        <b>🏆 Win Rate (vs ${cashoutPref}x):</b> ${winRate}%<br>
        <b>📈 Avg Multiplier:</b> ${avgMulti.toFixed(2)}x
      `;

      drawChart();
    }

    function drawChart() {
      const ctx = document.getElementById("historyChart").getContext("2d");
      if (window.chartInstance) window.chartInstance.destroy();
      window.chartInstance = new Chart(ctx, {
        type: 'line',
        data: {
          labels: history.map((_, i) => `Round ${i + 1}`),
          datasets: [{
            label: 'Multiplier',
            data: history,
            borderColor: '#0f0',
            backgroundColor: 'rgba(0,255,0,0.1)',
            tension: 0.3,
            fill: true,
            pointRadius: 3,
            pointHoverRadius: 5
          }]
        },
        options: {
          scales: {
            y: {
              beginAtZero: true,
              suggestedMax: 10
            }
          }
        }
      });
    }

    function exportHistory() {
      const csv = history.map((v, i) => `Round ${i + 1},${v}`).join("\n");
      const blob = new Blob([csv], { type: 'text/csv' });
      const url = URL.createObjectURL(blob);
      const a = document.createElement("a");
      a.href = url;
      a.download = "aviatrix_history.csv";
      document.body.appendChild(a);
      a.click();
      document.body.removeChild(a);
    }

    function clearHistory() {
      if (confirm("Are you sure?")) {
        history = [];
        localStorage.removeItem("aviatrix_history");
        document.getElementById("output").innerHTML = "🧹 Cleared.";
        document.getElementById("extraStats").innerHTML = "";
        drawChart();
      }
    }

    window.onload = drawChart;
  </script></body>
</html>
# Aviatrix Smart Predictor (Pattern-Based Helper)
def analyze_pattern(crash_values):
    low_crashes = sum(1 for x in crash_values if x < 1.5)
    high_crash = max(crash_values)
    suggestion = ""

    if low_crashes >= 3:
        suggestion = "⚠️ High chance of a big multiplier soon. Consider betting."
    elif high_crash > 20:
        suggestion = "❌ Big multiplier just hit. Expect low crashes. Wait."
    else:
        suggestion = "✅ Stable rounds. You can bet small at 1.80x–2.00x."

    return suggestion

def main():
    print("🎯 Aviatrix Predictor - Hollywood Bets")
    print("Enter last 5 crash multipliers (e.g. 1.1 2.5 1.3 1.4 3.0):")

    try:
        values = list(map(float, input("> ").split()))
        if len(values) != 5:
            print("❌ Please enter exactly 5 values.")
            return
        tip = analyze_pattern(values)
        print(f"\n📊 Analysis: {values}")
        print(f"💡 Suggestion: {tip}")

    except ValueError:
        print("❌ Invalid input. Use numbers only.")

if __name__ == "__main__":
    main()
