<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Nothing to see here</title>
  <style>
    html,body { height:100%; margin:0; background:#000; font-family:system-ui,Arial; color:#ddd; }
    .center {
      height:100%;
      display:flex;
      align-items:center;
      justify-content:center;
      flex-direction:column;
      gap:12px;
    }
    .fake-link {
      background:#111;
      padding:16px 22px;
      border-radius:10px;
      box-shadow:0 6px 18px rgba(0,0,0,.6);
      cursor:pointer;
      user-select:none;
    }

    /* jumpscare overlay (hidden until triggered) */
    #scare {
      position:fixed;
      inset:0;
      display:flex;
      align-items:center;
      justify-content:center;
      background:#000;
      z-index:9999;
      visibility:hidden;
      opacity:0;
      transition: opacity .12s ease;
    }
    #scare.visible { visibility:visible; opacity:1; }
    #scare img {
      max-width:100%;
      max-height:100%;
      transform: scale(1);
      transition: transform .06s ease;
    }

    /* subtle vibration effect */
    @keyframes shake {
      0% { transform: translate(0,0) rotate(0); }
      20% { transform: translate(-8px,6px) rotate(-6deg); }
      40% { transform: translate(10px,-6px) rotate(6deg); }
      60% { transform: translate(-6px,4px) rotate(-4deg); }
      80% { transform: translate(6px,-4px) rotate(4deg); }
      100% { transform: translate(0,0) rotate(0); }
    }
    .shake { animation: shake .45s linear; }
  </style>
</head>
<body>
  <div class="center">
    <div style="text-align:center;">
      <h2 style="margin:0 0 8px 0">Download ready</h2>
      <div class="fake-link" id="fakeLink">Click to view file</div>
      <p style="margin:10px 0 0 0; font-size:13px; color:#888">If nothing happens, click again.</p>
    </div>
  </div>

  <!-- overlay that becomes visible on trigger -->
  <div id="scare" role="region" aria-hidden="true">
    <img id="scareImg" src="scare.jpg" alt="" />
  </div>

  <!-- hidden audio element -->
  <audio id="scareAudio" src="scream.mp3" preload="auto"></audio>

  <script>
    const fake = document.getElementById('fakeLink');
    const scare = document.getElementById('scare');
    const img = document.getElementById('scareImg');
    const audio = document.getElementById('scareAudio');

    // main trigger: user click -> show overlay + play audio + try fullscreen
    function triggerJumpscare() {
      // show overlay
      scare.classList.add('visible');
      // try request fullscreen for effect (best-effort)
      try {
        if (document.documentElement.requestFullscreen) {
          document.documentElement.requestFullscreen().catch(()=>{});
        }
      } catch(e){}

      // small delay so the image is visible then play sound and shake
      setTimeout(()=> {
        // play audio (must be triggered by user gesture — click satisfies browser policies)
        audio.currentTime = 0;
        const playPromise = audio.play();
        if (playPromise !== undefined) {
          playPromise.catch(()=> {
            // if browser blocks playback, show a visible "Play sound" fallback
            showSoundFallback();
          });
        }
        // quick scale/shake
        img.classList.add('shake');
        setTimeout(()=> img.classList.remove('shake'), 520);
      }, 80);

      // optional: after some seconds, auto-hide and exit fullscreen
      setTimeout(()=> {
        scare.classList.remove('visible');
        if (document.fullscreenElement) {
          document.exitFullscreen().catch(()=>{});
        }
      }, 3500);
    }

    function showSoundFallback(){
      // create small button to allow user to explicitly play sound
      const btn = document.createElement('button');
      btn.textContent = 'Play sound';
      Object.assign(btn.style, {
        position:'fixed', bottom:'20px', left:'50%', transform:'translateX(-50%)',
        padding:'10px 16px', fontSize:'16px', zIndex:10001
      });
      btn.onclick = () => {
        audio.play().catch(()=>{});
        btn.remove();
      };
      document.body.appendChild(btn);
    }

    fake.addEventListener('click', triggerJumpscare);

    // Bonus: keyboard trigger (Enter) for testing
    document.addEventListener('keydown', e=>{
      if (e.key === 'Enter') triggerJumpscare();
    });
  </script>
</body>
</html>
