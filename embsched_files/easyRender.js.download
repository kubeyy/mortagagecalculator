function ChangeUrl(e) {
  history.pushState(null, null, e);
}
function renderPage(i) {
  (xmlhttp = window.XMLHttpRequest
    ? new XMLHttpRequest()
    : new ActiveXObject("Microsoft.XMLHTTP")),
    (xmlhttp.onreadystatechange = function () {
      if (4 == xmlhttp.readyState && 200 == xmlhttp.status) {
        ChangeUrl(i);
        const c = new DOMParser(),
          l = c.parseFromString(xmlhttp.responseText, "text/html");
        var t = l.head.classList,
          n = l.body.classList;
        document.querySelector("head").innerHTML = l.head.innerHTML;
        var r = l.getElementsByTagName("script");
        let e = [];
        for (var s = 0; s < r.length; s++) {
          var a,
            o = r[s];
          o.src &&
            !o.src.includes("easyRender.js") &&
            (((a = document.createElement("script")).src =
              o.src + "?" + new Date().getTime()),
            (a.async = o.async),
            (o = new Promise((e, t) => {
              (a.onload = e), (a.onerror = t);
            })),
            e.push(o),
            document.head.appendChild(a));
        }
        Promise.all(e)
          .then(() => {
            (document.querySelector("head").classList = t),
              (document.querySelector("body").classList = n),
              (document.querySelector("body").innerHTML = l.body.innerHTML);
          })
          .catch((e) => {
            console.error("Error loading scripts:", e);
          });
      }
    }),
    xmlhttp.open("GET", i, !1),
    xmlhttp.send();
}
function renderPageinDiv(c, l) {
  (xmlhttp = window.XMLHttpRequest
    ? new XMLHttpRequest()
    : new ActiveXObject("Microsoft.XMLHTTP")),
    (xmlhttp.onreadystatechange = function () {
      if (4 == xmlhttp.readyState && 200 == xmlhttp.status) {
        ChangeUrl(c);
        const a = new DOMParser(),
          o = a.parseFromString(xmlhttp.responseText, "text/html");
        o.head.classList, o.body.classList;
        document.getElementById(l).innerHTML = o.head.innerHTML;
        var t = o.getElementsByTagName("script");
        let e = [];
        for (var n = 0; n < t.length; n++) {
          var r,
            s = t[n];
          s.src &&
            !s.src.includes("easyRender.js") &&
            (((r = document.createElement("script")).src =
              s.src + "?" + new Date().getTime()),
            (r.async = s.async),
            (s = new Promise((e, t) => {
              (r.onload = e), (r.onerror = t);
            })),
            e.push(s),
            document.head.appendChild(r));
        }
        Promise.all(e)
          .then(() => {
            document.getElementById(l).innerHTML = o.body.innerHTML;
          })
          .catch((e) => {
            console.error("Error loading scripts:", e);
          });
      }
    }),
    xmlhttp.open("GET", c, !1),
    xmlhttp.send();
}
