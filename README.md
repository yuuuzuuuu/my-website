<!DOCTYPE html>
<html lang="en"><head>
    <style data-vite-theme="" data-inject-first="">:root {
      --background: 0 0% 100%;
--foreground: 20 14.3% 4.1%;
--muted: 60 4.8% 95.9%;
--muted-foreground: 25 5.3% 44.7%;
--popover: 0 0% 100%;
--popover-foreground: 20 14.3% 4.1%;
--card: 0 0% 100%;
--card-foreground: 20 14.3% 4.1%;
--border: 20 5.9% 90%;
--input: 20 5.9% 90%;
--primary: 154 42% 30%;
--primary-foreground: 147 17% 98%;
--secondary: 60 4.8% 95.9%;
--secondary-foreground: 24 9.8% 10%;
--accent: 60 4.8% 95.9%;
--accent-foreground: 24 9.8% 10%;
--destructive: 0 84.2% 60.2%;
--destructive-foreground: 60 9.1% 97.8%;
--ring: 20 14.3% 4.1%;
--radius: 0.5rem;
  }
  .dark {
      --background: 240 10% 3.9%;
--foreground: 0 0% 98%;
--muted: 240 3.7% 15.9%;
--muted-foreground: 240 5% 64.9%;
--popover: 240 10% 3.9%;
--popover-foreground: 0 0% 98%;
--card: 240 10% 3.9%;
--card-foreground: 0 0% 98%;
--border: 240 3.7% 15.9%;
--input: 240 3.7% 15.9%;
--primary: 154 42% 30%;
--primary-foreground: 147 17% 98%;
--secondary: 240 3.7% 15.9%;
--secondary-foreground: 0 0% 98%;
--accent: 240 3.7% 15.9%;
--accent-foreground: 0 0% 98%;
--destructive: 0 62.8% 30.6%;
--destructive-foreground: 0 0% 98%;
--ring: 240 4.9% 83.9%;
--radius: 0.5rem;
  }</style>

    <script type="module">
import { createHotContext } from "/@vite/client";
const hot = createHotContext("/__dummy__runtime-error-plugin");

function sendError(error) {
  if (!(error instanceof Error)) {
    error = new Error("(unknown runtime error)");
  }
  const serialized = {
    message: error.message,
    stack: error.stack,
  };
  hot.send("runtime-error-plugin:error", serialized);
}

window.addEventListener("error", (evt) => {
  sendError(evt.error);
});

window.addEventListener("unhandledrejection", (evt) => {
  sendError(evt.reason);
});
</script>

    <script type="module">
import RefreshRuntime from "/@react-refresh"
RefreshRuntime.injectIntoGlobalHook(window)
window.$RefreshReg$ = () => {}
window.$RefreshSig$ = () => (type) => type
window.__vite_plugin_react_preamble_installed__ = true
</script>
    <script type="module" src="/@vite/client"></script>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
    <title>BudgetKu - Aplikasi Manajemen Pengeluaran</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&amp;display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/remixicon/4.2.0/remixicon.min.css">
    <script type="module">"use strict";(()=>{var F="0.0.11";var T={HIGHLIGHT_COLOR:"#0079F2",HIGHLIGHT_BG:"#0079F210",ALLOWED_DOMAIN:".replit.dev"},I={highlighter:{position:"absolute",zIndex:Number.MAX_SAFE_INTEGER-3,boxSizing:"border-box",pointerEvents:"none",border:`2px solid ${T.HIGHLIGHT_COLOR}`,borderRadius:"4px",background:T.HIGHLIGHT_BG,transition:"opacity 0.2s",willChange:"opacity",opacity:"0"},label:{position:"absolute",backgroundColor:T.HIGHLIGHT_COLOR,color:"#FFFFFF",padding:"2px 6px",borderRadius:"4px",fontSize:"12px",fontFamily:"monospace",transform:"translateY(-100%)",marginTop:"-4px",zIndex:Number.MAX_SAFE_INTEGER-2,pointerEvents:"none",opacity:"0"}};function Le(e,n){return e[13]=1,e[14]=n>>8,e[15]=n&255,e[16]=n>>8,e[17]=n&255,e}var ne=112,re=72,oe=89,ie=115,W;function Ne(){let e=new Int32Array(256);for(let n=0;n<256;n++){let t=n;for(let r=0;r<8;r++)t=t&1?3988292384^t>>>1:t>>>1;e[n]=t}return e}function Ie(e){let n=-1;W||(W=Ne());for(let t=0;t<e.length;t++)n=W[(n^e[t])&255]^n>>>8;return n^-1}function xe(e){let n=e.length-1;for(let t=n;t>=4;t--)if(e[t-4]===9&&e[t-3]===ne&&e[t-2]===re&&e[t-1]===oe&&e[t]===ie)return t-3;return 0}function De(e,n,t=!1){let r=new Uint8Array(13);n*=39.3701,r[0]=ne,r[1]=re,r[2]=oe,r[3]=ie,r[4]=n>>>24,r[5]=n>>>16,r[6]=n>>>8,r[7]=n&255,r[8]=r[4],r[9]=r[5],r[10]=r[6],r[11]=r[7],r[12]=1;let s=Ie(r),i=new Uint8Array(4);if(i[0]=s>>>24,i[1]=s>>>16,i[2]=s>>>8,i[3]=s&255,t){let a=xe(e);return e.set(r,a),e.set(i,a+13),e}else{let a=new Uint8Array(4);a[0]=0,a[1]=0,a[2]=0,a[3]=9;let o=new Uint8Array(54);return o.set(e,0),o.set(a,33),o.set(r,37),o.set(i,50),o}}var se="[modern-screenshot]",A=typeof window<"u",_e=A&&"Worker"in window,Me=A&&"atob"in window,Wt=A&&"btoa"in window,j=A?window.navigator?.userAgent:"",ae=j.includes("Chrome"),O=j.includes("AppleWebKit")&&!ae,V=j.includes("Firefox"),He=e=>e&&"__CONTEXT__"in e,Re=e=>e.constructor.name==="CSSFontFaceRule",Pe=e=>e.constructor.name==="CSSImportRule",v=e=>e.nodeType===1,M=e=>typeof e.className=="object",le=e=>e.tagName==="image",Fe=e=>e.tagName==="use",x=e=>v(e)&&typeof e.style<"u"&&!M(e),Oe=e=>e.nodeType===8,ke=e=>e.nodeType===3,N=e=>e.tagName==="IMG",k=e=>e.tagName==="VIDEO",Be=e=>e.tagName==="CANVAS",Ue=e=>e.tagName==="TEXTAREA",$e=e=>e.tagName==="INPUT",We=e=>e.tagName==="STYLE",Ge=e=>e.tagName==="SCRIPT",je=e=>e.tagName==="SELECT",Ve=e=>e.tagName==="SLOT",ze=e=>e.tagName==="IFRAME",qe=(...e)=>console.warn(se,...e);function Xe(e){let n=e?.createElement?.("canvas");return n&&(n.height=n.width=1),!!n&&"toDataURL"in n&&!!n.toDataURL("image/webp").includes("image/webp")}var G=e=>e.startsWith("data:");function ce(e,n){if(e.match(/^[a-z]+:\/\//i))return e;if(A&&e.match(/^\/\//))return window.location.protocol+e;if(e.match(/^[a-z]+:/i)||!A)return e;let t=B().implementation.createHTMLDocument(),r=t.createElement("base"),s=t.createElement("a");return t.head.appendChild(r),t.body.appendChild(s),n&&(r.href=n),s.href=e,s.href}function B(e){return(e&&v(e)?e?.ownerDocument:e)??window.document}var U="http://www.w3.org/2000/svg";function Ye(e,n,t){let r=B(t).createElementNS(U,"svg");return r.setAttributeNS(null,"width",e.toString()),r.setAttributeNS(null,"height",n.toString()),r.setAttributeNS(null,"viewBox",`0 0 ${e} ${n}`),r}function Je(e,n){let t=new XMLSerializer().serializeToString(e);return n&&(t=t.replace(/[\u0000-\u0008\v\f\u000E-\u001F\uD800-\uDFFF\uFFFE\uFFFF]/gu,"")),`data:image/svg+xml;charset=utf-8,${encodeURIComponent(t)}`}async function Ke(e,n="image/png",t=1){try{return await new Promise((r,s)=>{e.toBlob(i=>{i?r(i):s(new Error("Blob is null"))},n,t)})}catch(r){if(Me)return Qe(e.toDataURL(n,t));throw r}}function Qe(e){let[n,t]=e.split(","),r=n.match(/data:(.+);/)?.[1]??void 0,s=window.atob(t),i=s.length,a=new Uint8Array(i);for(let o=0;o<i;o+=1)a[o]=s.charCodeAt(o);return new Blob([a],{type:r})}function ue(e,n){return new Promise((t,r)=>{let s=new FileReader;s.onload=()=>t(s.result),s.onerror=()=>r(s.error),s.onabort=()=>r(new Error(`Failed read blob to ${n}`)),n==="dataUrl"?s.readAsDataURL(e):n==="arrayBuffer"&&s.readAsArrayBuffer(e)})}var Ze=e=>ue(e,"dataUrl"),et=e=>ue(e,"arrayBuffer");function L(e,n){let t=B(n).createElement("img");return t.decoding="sync",t.loading="eager",t.src=e,t}function D(e,n){return new Promise(t=>{let{timeout:r,ownerDocument:s,onError:i,onWarn:a}=n??{},o=typeof e=="string"?L(e,B(s)):e,c=null,d=null;function l(){t(o),c&&clearTimeout(c),d?.()}if(r&&(c=setTimeout(l,r)),k(o)){let u=o.currentSrc||o.src;if(!u)return o.poster?D(o.poster,n).then(t):l();if(o.readyState>=2)return l();let h=l,f=g=>{a?.("Failed video load",u,g),i?.(g),l()};d=()=>{o.removeEventListener("loadeddata",h),o.removeEventListener("error",f)},o.addEventListener("loadeddata",h,{once:!0}),o.addEventListener("error",f,{once:!0})}else{let u=le(o)?o.href.baseVal:o.currentSrc||o.src;if(!u)return l();let h=async()=>{if(N(o)&&"decode"in o)try{await o.decode()}catch(g){a?.("Failed to decode image, trying to render anyway",o.dataset.originalSrc||u,g)}l()},f=g=>{a?.("Failed image load",o.dataset.originalSrc||u,g),l()};if(N(o)&&o.complete)return h();d=()=>{o.removeEventListener("load",h),o.removeEventListener("error",f)},o.addEventListener("load",h,{once:!0}),o.addEventListener("error",f,{once:!0})}})}async function tt(e,n){x(e)&&(N(e)||k(e)?await D(e,n):await Promise.all(["img","video"].flatMap(t=>Array.from(e.querySelectorAll(t)).map(r=>D(r,n)))))}var de=function(){let n=0,t=()=>`0000${(Math.random()*36**4<<0).toString(36)}`.slice(-4);return()=>(n+=1,`u${t()}${n}`)}();function he(e){return e?.split(",").map(n=>n.trim().replace(/"|'/g,"").toLowerCase()).filter(Boolean)}var J=0;function nt(e){let n=`${se}[#${J}]`;return J++,{time:t=>e&&console.time(`${n} ${t}`),timeEnd:t=>e&&console.timeEnd(`${n} ${t}`),warn:(...t)=>e&&qe(...t)}}function rt(e){return{cache:e?"no-cache":"force-cache"}}async function z(e,n){return He(e)?e:ot(e,{...n,autoDestruct:!0})}async function ot(e,n){let{scale:t=1,workerUrl:r,workerNumber:s=1}=n||{},i=!!n?.debug,a=n?.features??!0,o=e.ownerDocument??(A?window.document:void 0),c=e.ownerDocument?.defaultView??(A?window:void 0),d=new Map,l={width:0,height:0,quality:1,type:"image/png",scale:t,backgroundColor:null,style:null,filter:null,maximumCanvasSize:0,timeout:3e4,progress:null,debug:i,fetch:{requestInit:rt(n?.fetch?.bypassingCache),placeholderImage:"data:image/png;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7",bypassingCache:!1,...n?.fetch},fetchFn:null,font:{},drawImageInterval:100,workerUrl:null,workerNumber:s,onCloneNode:null,onEmbedNode:null,onCreateForeignObjectSvg:null,includeStyleProperties:null,autoDestruct:!1,...n,__CONTEXT__:!0,log:nt(i),node:e,ownerDocument:o,ownerWindow:c,dpi:t===1?null:96*t,svgStyleElement:ge(o),svgDefsElement:o?.createElementNS(U,"defs"),svgStyles:new Map,defaultComputedStyles:new Map,workers:[...Array.from({length:_e&&r&&s?s:0})].map(()=>{try{let f=new Worker(r);return f.onmessage=async g=>{let{url:m,result:p}=g.data;p?d.get(m)?.resolve?.(p):d.get(m)?.reject?.(new Error(`Error receiving message from worker: ${m}`))},f.onmessageerror=g=>{let{url:m}=g.data;d.get(m)?.reject?.(new Error(`Error receiving message from worker: ${m}`))},f}catch(f){return l.log.warn("Failed to new Worker",f),null}}).filter(Boolean),fontFamilies:new Map,fontCssTexts:new Map,acceptOfImage:`${[Xe(o)&&"image/webp","image/svg+xml","image/*","*/*"].filter(Boolean).join(",")};q=0.8`,requests:d,drawImageCount:0,tasks:[],features:a,isEnable:f=>f==="restoreScrollPosition"?typeof a=="boolean"?!1:a[f]??!1:typeof a=="boolean"?a:a[f]??!0};l.log.time("wait until load"),await tt(e,{timeout:l.timeout,onWarn:l.log.warn}),l.log.timeEnd("wait until load");let{width:u,height:h}=it(e,l);return l.width=u,l.height=h,l}function ge(e){if(!e)return;let n=e.createElement("style"),t=n.ownerDocument.createTextNode(`
.______background-clip--text {
  background-clip: text;
  -webkit-background-clip: text;
}
`);return n.appendChild(t),n}function it(e,n){let{width:t,height:r}=n;if(v(e)&&(!t||!r)){let s=e.getBoundingClientRect();t=t||s.width||Number(e.getAttribute("width"))||0,r=r||s.height||Number(e.getAttribute("height"))||0}return{width:t,height:r}}async function st(e,n){let{log:t,timeout:r,drawImageCount:s,drawImageInterval:i}=n;t.time("image to canvas");let a=await D(e,{timeout:r,onWarn:n.log.warn}),{canvas:o,context2d:c}=at(e.ownerDocument,n),d=()=>{try{c?.drawImage(a,0,0,o.width,o.height)}catch(l){n.log.warn("Failed to drawImage",l)}};if(d(),n.isEnable("fixSvgXmlDecode"))for(let l=0;l<s;l++)await new Promise(u=>{setTimeout(()=>{d(),u()},l+i)});return n.drawImageCount=0,t.timeEnd("image to canvas"),o}function at(e,n){let{width:t,height:r,scale:s,backgroundColor:i,maximumCanvasSize:a}=n,o=e.createElement("canvas");o.width=Math.floor(t*s),o.height=Math.floor(r*s),o.style.width=`${t}px`,o.style.height=`${r}px`,a&&(o.width>a||o.height>a)&&(o.width>a&&o.height>a?o.width>o.height?(o.height*=a/o.width,o.width=a):(o.width*=a/o.height,o.height=a):o.width>a?(o.height*=a/o.width,o.width=a):(o.width*=a/o.height,o.height=a));let c=o.getContext("2d");return c&&i&&(c.fillStyle=i,c.fillRect(0,0,o.width,o.height)),{canvas:o,context2d:c}}function fe(e,n){if(e.ownerDocument)try{let i=e.toDataURL();if(i!=="data:,")return L(i,e.ownerDocument)}catch(i){n.log.warn("Failed to clone canvas",i)}let t=e.cloneNode(!1),r=e.getContext("2d"),s=t.getContext("2d");try{return r&&s&&s.putImageData(r.getImageData(0,0,e.width,e.height),0,0),t}catch(i){n.log.warn("Failed to clone canvas",i)}return t}function lt(e,n){try{if(e?.contentDocument?.body)return q(e.contentDocument.body,n)}catch(t){n.log.warn("Failed to clone iframe",t)}return e.cloneNode(!1)}function ct(e){let n=e.cloneNode(!1);return e.currentSrc&&e.currentSrc!==e.src&&(n.src=e.currentSrc,n.srcset=""),n.loading==="lazy"&&(n.loading="eager"),n}async function ut(e,n){if(e.ownerDocument&&!e.currentSrc&&e.poster)return L(e.poster,e.ownerDocument);let t=e.cloneNode(!1);t.crossOrigin="anonymous",e.currentSrc&&e.currentSrc!==e.src&&(t.src=e.currentSrc);let r=t.ownerDocument;if(r){let s=!0;if(await D(t,{onError:()=>s=!1,onWarn:n.log.warn}),!s)return e.poster?L(e.poster,e.ownerDocument):t;t.currentTime=e.currentTime,await new Promise(a=>{t.addEventListener("seeked",a,{once:!0})});let i=r.createElement("canvas");i.width=e.offsetWidth,i.height=e.offsetHeight;try{let a=i.getContext("2d");a&&a.drawImage(t,0,0,i.width,i.height)}catch(a){return n.log.warn("Failed to clone video",a),e.poster?L(e.poster,e.ownerDocument):t}return fe(i,n)}return t}function dt(e,n){return Be(e)?fe(e,n):ze(e)?lt(e,n):N(e)?ct(e):k(e)?ut(e,n):e.cloneNode(!1)}function ht(e){let n=e.sandbox;if(!n){let{ownerDocument:t}=e;try{t&&(n=t.createElement("iframe"),n.id=`__SANDBOX__-${de()}`,n.width="0",n.height="0",n.style.visibility="hidden",n.style.position="fixed",t.body.appendChild(n),n.contentWindow?.document.write('<!DOCTYPE html><meta charset="UTF-8"><title></title><body>'),e.sandbox=n)}catch(r){e.log.warn("Failed to getSandBox",r)}}return n}var gt=["width","height","-webkit-text-fill-color"],ft=["stroke","fill"];function me(e,n,t){let{defaultComputedStyles:r}=t,s=e.nodeName.toLowerCase(),i=M(e)&&s!=="svg",a=i?ft.map(m=>[m,e.getAttribute(m)]).filter(([,m])=>m!==null):[],o=[i&&"svg",s,a.map((m,p)=>`${m}=${p}`).join(","),n].filter(Boolean).join(":");if(r.has(o))return r.get(o);let d=ht(t)?.contentWindow;if(!d)return new Map;let l=d?.document,u,h;i?(u=l.createElementNS(U,"svg"),h=u.ownerDocument.createElementNS(u.namespaceURI,s),a.forEach(([m,p])=>{h.setAttributeNS(null,m,p)}),u.appendChild(h)):u=h=l.createElement(s),h.textContent=" ",l.body.appendChild(u);let f=d.getComputedStyle(h,n),g=new Map;for(let m=f.length,p=0;p<m;p++){let w=f.item(p);gt.includes(w)||g.set(w,f.getPropertyValue(w))}return l.body.removeChild(u),r.set(o,g),g}function pe(e,n,t){let r=new Map,s=[],i=new Map;if(t)for(let o of t)a(o);else for(let o=e.length,c=0;c<o;c++){let d=e.item(c);a(d)}for(let o=s.length,c=0;c<o;c++)i.get(s[c])?.forEach((d,l)=>r.set(l,d));function a(o){let c=e.getPropertyValue(o),d=e.getPropertyPriority(o),l=o.lastIndexOf("-"),u=l>-1?o.substring(0,l):void 0;if(u){let h=i.get(u);h||(h=new Map,i.set(u,h)),h.set(o,[c,d])}n.get(o)===c&&!d||(u?s.push(u):r.set(o,[c,d]))}return r}function mt(e,n,t,r){let{ownerWindow:s,includeStyleProperties:i,currentParentNodeStyle:a}=r,o=n.style,c=s.getComputedStyle(e),d=me(e,null,r);a?.forEach((u,h)=>{d.delete(h)});let l=pe(c,d,i);l.delete("transition-property"),l.delete("all"),l.delete("d"),l.delete("content"),t&&(l.delete("margin-top"),l.delete("margin-right"),l.delete("margin-bottom"),l.delete("margin-left"),l.delete("margin-block-start"),l.delete("margin-block-end"),l.delete("margin-inline-start"),l.delete("margin-inline-end"),l.set("box-sizing",["border-box",""])),l.get("background-clip")?.[0]==="text"&&n.classList.add("______background-clip--text"),ae&&(l.has("font-kerning")||l.set("font-kerning",["normal",""]),(l.get("overflow-x")?.[0]==="hidden"||l.get("overflow-y")?.[0]==="hidden")&&l.get("text-overflow")?.[0]==="ellipsis"&&e.scrollWidth===e.clientWidth&&l.set("text-overflow",["clip",""]));for(let u=o.length,h=0;h<u;h++)o.removeProperty(o.item(h));return l.forEach(([u,h],f)=>{o.setProperty(f,u,h)}),l}function pt(e,n){(Ue(e)||$e(e)||je(e))&&n.setAttribute("value",e.value)}var wt=[":before",":after"],bt=[":-webkit-scrollbar",":-webkit-scrollbar-button",":-webkit-scrollbar-thumb",":-webkit-scrollbar-track",":-webkit-scrollbar-track-piece",":-webkit-scrollbar-corner",":-webkit-resizer"];function Et(e,n,t,r,s){let{ownerWindow:i,svgStyleElement:a,svgStyles:o,currentNodeStyle:c}=r;if(!a||!i)return;function d(l){let u=i.getComputedStyle(e,l),h=u.getPropertyValue("content");if(!h||h==="none")return;s?.(h),h=h.replace(/(')|(")|(counter\(.+\))/g,"");let f=[de()],g=me(e,l,r);c?.forEach((b,y)=>{g.delete(y)});let m=pe(u,g,r.includeStyleProperties);m.delete("content"),m.delete("-webkit-locale"),m.get("background-clip")?.[0]==="text"&&n.classList.add("______background-clip--text");let p=[`content: '${h}';`];if(m.forEach(([b,y],C)=>{p.push(`${C}: ${b}${y?" !important":""};`)}),p.length===1)return;try{n.className=[n.className,...f].join(" ")}catch(b){r.log.warn("Failed to copyPseudoClass",b);return}let w=p.join(`
  `),E=o.get(w);E||(E=[],o.set(w,E)),E.push(`.${f[0]}:${l}`)}wt.forEach(d),t&&bt.forEach(d)}var K=new Set(["symbol"]);async function Q(e,n,t,r,s){if(v(t)&&(We(t)||Ge(t))||r.filter&&!r.filter(t))return;K.has(n.nodeName)||K.has(t.nodeName)?r.currentParentNodeStyle=void 0:r.currentParentNodeStyle=r.currentNodeStyle;let i=await q(t,r,!1,s);r.isEnable("restoreScrollPosition")&&yt(e,i),n.appendChild(i)}async function Z(e,n,t,r){let s=(v(e)?e.shadowRoot?.firstChild:void 0)??e.firstChild;for(let i=s;i;i=i.nextSibling)if(!Oe(i))if(v(i)&&Ve(i)&&typeof i.assignedNodes=="function"){let a=i.assignedNodes();for(let o=0;o<a.length;o++)await Q(e,n,a[o],t,r)}else await Q(e,n,i,t,r)}function yt(e,n){if(!x(e)||!x(n))return;let{scrollTop:t,scrollLeft:r}=e;if(!t&&!r)return;let{transform:s}=n.style,i=new DOMMatrix(s),{a,b:o,c,d}=i;i.a=1,i.b=0,i.c=0,i.d=1,i.translateSelf(-r,-t),i.a=a,i.b=o,i.c=c,i.d=d,n.style.transform=i.toString()}function vt(e,n){let{backgroundColor:t,width:r,height:s,style:i}=n,a=e.style;if(t&&a.setProperty("background-color",t,"important"),r&&a.setProperty("width",`${r}px`,"important"),s&&a.setProperty("height",`${s}px`,"important"),i)for(let o in i)a[o]=i[o]}var St=/^[\w-:]+$/;async function q(e,n,t=!1,r){let{ownerDocument:s,ownerWindow:i,fontFamilies:a}=n;if(s&&ke(e))return r&&/\S/.test(e.data)&&r(e.data),s.createTextNode(e.data);if(s&&i&&v(e)&&(x(e)||M(e))){let c=await dt(e,n);if(n.isEnable("removeAbnormalAttributes")){let g=c.getAttributeNames();for(let m=g.length,p=0;p<m;p++){let w=g[p];St.test(w)||c.removeAttribute(w)}}let d=n.currentNodeStyle=mt(e,c,t,n);t&&vt(c,n);let l=!1;if(n.isEnable("copyScrollbar")){let g=[d.get("overflow-x")?.[0],d.get("overflow-y")?.[0]];l=g.includes("scroll")||(g.includes("auto")||g.includes("overlay"))&&(e.scrollHeight>e.clientHeight||e.scrollWidth>e.clientWidth)}let u=d.get("text-transform")?.[0],h=he(d.get("font-family")?.[0]),f=h?g=>{u==="uppercase"?g=g.toUpperCase():u==="lowercase"?g=g.toLowerCase():u==="capitalize"&&(g=g[0].toUpperCase()+g.substring(1)),h.forEach(m=>{let p=a.get(m);p||a.set(m,p=new Set),g.split("").forEach(w=>p.add(w))})}:void 0;return Et(e,c,l,n,f),pt(e,c),k(e)||await Z(e,c,n,f),c}let o=e.cloneNode(!1);return await Z(e,o,n),o}function Ct(e){if(e.ownerDocument=void 0,e.ownerWindow=void 0,e.svgStyleElement=void 0,e.svgDefsElement=void 0,e.svgStyles.clear(),e.defaultComputedStyles.clear(),e.sandbox){try{e.sandbox.remove()}catch(n){e.log.warn("Failed to destroyContext",n)}e.sandbox=void 0}e.workers=[],e.fontFamilies.clear(),e.fontCssTexts.clear(),e.requests.clear(),e.tasks=[]}function Tt(e){let{url:n,timeout:t,responseType:r,...s}=e,i=new AbortController,a=t?setTimeout(()=>i.abort(),t):void 0;return fetch(n,{signal:i.signal,...s}).then(o=>{if(!o.ok)throw new Error("Failed fetch, not 2xx response",{cause:o});switch(r){case"arrayBuffer":return o.arrayBuffer();case"dataUrl":return o.blob().then(Ze);case"text":default:return o.text()}}).finally(()=>clearTimeout(a))}function _(e,n){let{url:t,requestType:r="text",responseType:s="text",imageDom:i}=n,a=t,{timeout:o,acceptOfImage:c,requests:d,fetchFn:l,fetch:{requestInit:u,bypassingCache:h,placeholderImage:f},font:g,workers:m,fontFamilies:p}=e;r==="image"&&(O||V)&&e.drawImageCount++;let w=d.get(t);if(!w){h&&h instanceof RegExp&&h.test(a)&&(a+=(/\?/.test(a)?"&":"?")+new Date().getTime());let E=r.startsWith("font")&&g&&g.minify,b=new Set;E&&r.split(";")[1].split(",").forEach(P=>{p.has(P)&&p.get(P).forEach(Y=>b.add(Y))});let y=E&&b.size,C={url:a,timeout:o,responseType:y?"arrayBuffer":s,headers:r==="image"?{accept:c}:void 0,...u};w={type:r,resolve:void 0,reject:void 0,response:null},w.response=(async()=>{if(l&&r==="image"){let S=await l(t);if(S)return S}return!O&&t.startsWith("http")&&m.length?new Promise((S,P)=>{m[d.size&m.length-1].postMessage({rawUrl:t,...C}),w.resolve=S,w.reject=P}):Tt(C)})().catch(S=>{if(d.delete(t),r==="image"&&f)return e.log.warn("Failed to fetch image base64, trying to use placeholder image",a),typeof f=="string"?f:f(i);throw S}),d.set(t,w)}return w.response}async function we(e,n,t,r){if(!be(e))return e;for(let[s,i]of At(e,n))try{let a=await _(t,{url:i,requestType:r?"image":"text",responseType:"dataUrl"});e=e.replace(Lt(s),`$1${a}$3`)}catch(a){t.log.warn("Failed to fetch css data url",s,a)}return e}function be(e){return/url\((['"]?)([^'"]+?)\1\)/.test(e)}var Ee=/url\((['"]?)([^'"]+?)\1\)/g;function At(e,n){let t=[];return e.replace(Ee,(r,s,i)=>(t.push([i,ce(i,n)]),r)),t.filter(([r])=>!G(r))}function Lt(e){let n=e.replace(/([.*+?^${}()|\[\]\/\\])/g,"\\$1");return new RegExp(`(url\\(['"]?)(${n})(['"]?\\))`,"g")}var Nt=["background-image","border-image-source","-webkit-border-image","-webkit-mask-image","list-style-image"];function It(e,n){return Nt.map(t=>{let r=e.getPropertyValue(t);return!r||r==="none"?null:((O||V)&&n.drawImageCount++,we(r,null,n,!0).then(s=>{!s||r===s||e.setProperty(t,s,e.getPropertyPriority(t))}))}).filter(Boolean)}function xt(e,n){if(N(e)){let t=e.currentSrc||e.src;if(!G(t))return[_(n,{url:t,imageDom:e,requestType:"image",responseType:"dataUrl"}).then(r=>{r&&(e.srcset="",e.dataset.originalSrc=t,e.src=r||"")})];(O||V)&&n.drawImageCount++}else if(M(e)&&!G(e.href.baseVal)){let t=e.href.baseVal;return[_(n,{url:t,imageDom:e,requestType:"image",responseType:"dataUrl"}).then(r=>{r&&(e.dataset.originalSrc=t,e.href.baseVal=r||"")})]}return[]}function Dt(e,n){let{ownerDocument:t,svgDefsElement:r}=n,s=e.getAttribute("href")??e.getAttribute("xlink:href");if(!s)return[];let[i,a]=s.split("#");if(a){let o=`#${a}`,c=t?.querySelector(`svg ${o}`);if(i&&e.setAttribute("href",o),r?.querySelector(o))return[];if(c)return r?.appendChild(c.cloneNode(!0)),[];if(i)return[_(n,{url:i,responseType:"text"}).then(d=>{r?.insertAdjacentHTML("beforeend",d)})]}return[]}function ye(e,n){let{tasks:t}=n;v(e)&&((N(e)||le(e))&&t.push(...xt(e,n)),Fe(e)&&t.push(...Dt(e,n))),x(e)&&t.push(...It(e.style,n)),e.childNodes.forEach(r=>{ye(r,n)})}async function _t(e,n){let{ownerDocument:t,svgStyleElement:r,fontFamilies:s,fontCssTexts:i,tasks:a,font:o}=n;if(!(!t||!r||!s.size))if(o&&o.cssText){let c=te(o.cssText,n);r.appendChild(t.createTextNode(`${c}
`))}else{let c=Array.from(t.styleSheets).filter(l=>{try{return"cssRules"in l&&!!l.cssRules.length}catch(u){return n.log.warn(`Error while reading CSS rules from ${l.href}`,u),!1}});await Promise.all(c.flatMap(l=>Array.from(l.cssRules).map(async(u,h)=>{if(Pe(u)){let f=h+1,g=u.href,m="";try{m=await _(n,{url:g,requestType:"text",responseType:"text"})}catch(w){n.log.warn(`Error fetch remote css import from ${g}`,w)}let p=m.replace(Ee,(w,E,b)=>w.replace(b,ce(b,g)));for(let w of Ht(p))try{l.insertRule(w,w.startsWith("@import")?f+=1:l.cssRules.length)}catch(E){n.log.warn("Error inserting rule from remote css import",{rule:w,error:E})}}}))),c.flatMap(l=>Array.from(l.cssRules)).filter(l=>Re(l)&&be(l.style.getPropertyValue("src"))&&he(l.style.getPropertyValue("font-family"))?.some(u=>s.has(u))).forEach(l=>{let u=l,h=i.get(u.cssText);h?r.appendChild(t.createTextNode(`${h}
`)):a.push(we(u.cssText,u.parentStyleSheet?u.parentStyleSheet.href:null,n).then(f=>{f=te(f,n),i.set(u.cssText,f),r.appendChild(t.createTextNode(`${f}
`))}))})}}var Mt=/(\/\*[\s\S]*?\*\/)/g,ee=/((@.*?keyframes [\s\S]*?){([\s\S]*?}\s*?)})/gi;function Ht(e){if(e==null)return[];let n=[],t=e.replace(Mt,"");for(;;){let i=ee.exec(t);if(!i)break;n.push(i[0])}t=t.replace(ee,"");let r=/@import[\s\S]*?url\([^)]*\)[\s\S]*?;/gi,s=new RegExp("((\\s*?(?:\\/\\*[\\s\\S]*?\\*\\/)?\\s*?@media[\\s\\S]*?){([\\s\\S]*?)}\\s*?})|(([\\s\\S]*?){([\\s\\S]*?)})","gi");for(;;){let i=r.exec(t);if(i)s.lastIndex=r.lastIndex;else if(i=s.exec(t),i)r.lastIndex=s.lastIndex;else break;n.push(i[0])}return n}var Rt=/url\([^)]+\)\s*format\((["']?)([^"']+)\1\)/g,Pt=/src:\s*(?:url\([^)]+\)\s*format\([^)]+\)[,;]\s*)+/g;function te(e,n){let{font:t}=n,r=t?t?.preferredFormat:void 0;return r?e.replace(Pt,s=>{for(;;){let[i,,a]=Rt.exec(s)||[];if(!a)return"";if(a===r)return`src: ${i};`}}):e}async function Ft(e,n){let t=await z(e,n);if(v(t.node)&&M(t.node))return t.node;let{ownerDocument:r,log:s,tasks:i,svgStyleElement:a,svgDefsElement:o,svgStyles:c,font:d,progress:l,autoDestruct:u,onCloneNode:h,onEmbedNode:f,onCreateForeignObjectSvg:g}=t;s.time("clone node");let m=await q(t.node,t,!0);if(a&&r){let y="";c.forEach((C,S)=>{y+=`${C.join(`,
`)} {
  ${S}
}
`}),a.appendChild(r.createTextNode(y))}s.timeEnd("clone node"),await h?.(m),d!==!1&&v(m)&&(s.time("embed web font"),await _t(m,t),s.timeEnd("embed web font")),s.time("embed node"),ye(m,t);let p=i.length,w=0,E=async()=>{for(;;){let y=i.pop();if(!y)break;try{await y}catch(C){t.log.warn("Failed to run task",C)}l?.(++w,p)}};l?.(w,p),await Promise.all([...Array.from({length:4})].map(E)),s.timeEnd("embed node"),await f?.(m);let b=Ot(m,t);return o&&b.insertBefore(o,b.children[0]),a&&b.insertBefore(a,b.children[0]),u&&Ct(t),await g?.(b),b}function Ot(e,n){let{width:t,height:r}=n,s=Ye(t,r,e.ownerDocument),i=s.ownerDocument.createElementNS(s.namespaceURI,"foreignObject");return i.setAttributeNS(null,"x","0%"),i.setAttributeNS(null,"y","0%"),i.setAttributeNS(null,"width","100%"),i.setAttributeNS(null,"height","100%"),i.append(e),s.appendChild(i),s}async function kt(e,n){let t=await z(e,n),r=await Ft(t),s=Je(r,t.isEnable("removeControlCharacter"));t.autoDestruct||(t.svgStyleElement=ge(t.ownerDocument),t.svgDefsElement=t.ownerDocument?.createElementNS(U,"defs"),t.svgStyles.clear());let i=L(s,r.ownerDocument);return await st(i,t)}async function ve(e,n){let t=await z(e,n),{log:r,type:s,quality:i,dpi:a}=t,o=await kt(t);r.time("canvas to blob");let c=await Ke(o,s,i);if(["image/png","image/jpeg"].includes(s)&&a){let d=await et(c.slice(0,33)),l=new Uint8Array(d);return s==="image/png"?l=De(l,a):s==="image/jpeg"&&(l=Le(l,a)),r.timeEnd("canvas to blob"),new Blob([l,c.slice(33)],{type:s})}return r.timeEnd("canvas to blob"),c}var H={METADATA:"data-replit-metadata",COMPONENT_NAME:"data-component-name"};function Se(e){if(e.startsWith("http://localhost:"))return!0;try{return new URL(e).hostname.endsWith(T.ALLOWED_DOMAIN)}catch{return!1}}function Ce(e){return e?document.elementFromPoint(e.clientX,e.clientY):null}function X(e){return!!(e.getAttribute(H.METADATA)&&e.getAttribute(H.COMPONENT_NAME))}function $(e){let n={elementPath:e.getAttribute(H.METADATA)??"",elementName:e.getAttribute(H.COMPONENT_NAME)??"",textContent:e.textContent??"",tag:e.tagName.toLowerCase()};return n.textContent.length>100&&(n.textContent=n.textContent.slice(0,100)+"..."),n}async function Te(e){try{let t=window.getComputedStyle(e).backgroundColor;return Bt(t)&&(t=window.getComputedStyle(document.documentElement).backgroundColor),await ve(e,{type:"image/png",backgroundColor:t,fetch:{requestInit:{mode:"no-cors"}}})}catch(n){console.error("[replit-cartographer] Failed to take screenshot:",n);return}}function Bt(e){return e==="transparent"||e==="rgba(0, 0, 0, 0)"||e.endsWith(", 0)")||e.endsWith(",0)")}var R=class{selectedElement=null;isActive=!1;lastHighlightedElement=null;hoverHighlighter=null;hoverLabel=null;selectedHighlighter=null;selectedLabel=null;constructor(){this.setupMessageListener(),this.notifyScriptLoaded()}initializeHighlighter(){this.hoverHighlighter=document.createElement("div"),this.hoverLabel=document.createElement("div"),Object.assign(this.hoverHighlighter.style,{...I.highlighter,zIndex:Number.MAX_SAFE_INTEGER,pointerEvents:"all",position:"fixed"}),Object.assign(this.hoverLabel.style,{...I.label,zIndex:Number.MAX_SAFE_INTEGER,pointerEvents:"all",position:"fixed"}),this.selectedHighlighter=document.createElement("div"),this.selectedLabel=document.createElement("div"),Object.assign(this.selectedHighlighter.style,{...I.highlighter,pointerEvents:"none",position:"fixed"}),Object.assign(this.selectedLabel.style,{...I.label,pointerEvents:"none",position:"fixed"}),document.body.appendChild(this.selectedHighlighter),document.body.appendChild(this.selectedLabel),document.body.appendChild(this.hoverHighlighter),document.body.appendChild(this.hoverLabel)}setupMessageListener(){window.addEventListener("message",this.handleMessage.bind(this))}notifyScriptLoaded(){this.postMessageToParent({type:"SELECTOR_SCRIPT_LOADED",timestamp:Date.now(),version:F})}postMessageToParent(n){window.parent&&window.parent.postMessage(n,"*")}handleMouseMove=n=>{if(this.isActive&&this.hoverHighlighter){this.hoverHighlighter.style.pointerEvents="none";let t=Ce(n);if(!t||t===this.hoverHighlighter||t===this.selectedHighlighter||!X(t)){this.hideHighlight(this.hoverHighlighter,this.hoverLabel),this.lastHighlightedElement=null;return}this.lastHighlightedElement=t,this.hoverHighlighter.style.pointerEvents="all",this.hoverHighlighter.style.border=`2px dashed ${T.HIGHLIGHT_COLOR}`,this.updateHighlighterPosition(t,this.hoverHighlighter,this.hoverLabel)}};handleMouseLeave=()=>{this.isActive&&this.hideHighlight(this.hoverHighlighter,this.hoverLabel)};calculateLabelPosition(n,t){return t<24?{top:`${t+window.scrollY}px`,left:`${n.left+window.scrollX}px`,transform:"none",marginTop:"2px"}:{top:`${t+window.scrollY}px`,left:`${n.left+window.scrollX}px`,transform:"translateY(-100%)",marginTop:"-4px"}}updateHighlighterPosition(n,t,r){if(!t||!r)return;let s=n.getBoundingClientRect(),i=window.innerHeight,a=Math.max(0,s.top),o=Math.min(i,s.bottom),c=Math.max(0,o-a);Object.assign(t.style,{opacity:c>0?"1":"0",top:`${a}px`,left:`${s.left}px`,width:`${s.width}px`,height:`${c}px`});let d=$(n);r.textContent=d.elementName;let l=this.calculateLabelPosition(s,a);l.top=`${a}px`,l.left=`${s.left}px`,Object.assign(r.style,{...l,opacity:c>0?"1":"0"})}hideHighlight(n,t){n&&(n.style.opacity="0"),t&&(t.style.opacity="0")}handleClick=async n=>{if(!this.isActive)return;n.preventDefault(),n.stopPropagation();let t=this.lastHighlightedElement;if(!t||!X(t))return;if(t===this.selectedElement){this.unselectCurrentElement(),this.hideHighlight(this.selectedHighlighter,this.selectedLabel),this.postMessageToParent({type:"ELEMENT_UNSELECTED",timestamp:Date.now()});return}this.selectedElement=t,this.selectedHighlighter&&this.selectedLabel&&(this.selectedHighlighter.style.border=`2px solid ${T.HIGHLIGHT_COLOR}`,this.selectedHighlighter.style.opacity="1",this.selectedLabel.style.opacity="1",this.selectedLabel.textContent=$(t).elementName),this.updateHighlighterPosition(t,this.selectedHighlighter,this.selectedLabel);let r=$(t),s=await Te(t);this.postMessageToParent({type:"ELEMENT_SELECTED",payload:{...r,screenshotBlob:s},timestamp:Date.now()})};unselectCurrentElement(){this.selectedElement&&(this.selectedElement=null)}handleMessage=n=>{if(!Se(n.origin))return;let t=n.data;if(!(!t||typeof t!="object"))switch(t.type){case"TOGGLE_REPLIT_VISUAL_EDITOR":{this.handleVisualEditorToggle(t.enabled);break}case"CLEAR_SELECTION":{this.unselectCurrentElement(),this.hideHighlight(this.selectedHighlighter,this.selectedLabel);break}}};handleVisualEditorToggle(n){let t=!!n;t?this.postMessageToParent({type:"REPLIT_VISUAL_EDITOR_ENABLED",timestamp:Date.now()}):this.postMessageToParent({type:"REPLIT_VISUAL_EDITOR_DISABLED",timestamp:Date.now()}),this.isActive!==t&&(this.isActive=t,this.toggleEventListeners(t))}recalculateSelectedElement=()=>{this.isActive&&(this.selectedElement&&this.updateHighlighterPosition(this.selectedElement,this.selectedHighlighter,this.selectedLabel),this.lastHighlightedElement&&this.updateHighlighterPosition(this.lastHighlightedElement,this.hoverHighlighter,this.hoverLabel))};toggleEventListeners(n){n?(this.initializeHighlighter(),document.addEventListener("mousemove",this.handleMouseMove),document.addEventListener("mouseleave",this.handleMouseLeave),document.addEventListener("click",this.handleClick,!0),window.addEventListener("resize",this.recalculateSelectedElement),window.addEventListener("scroll",this.recalculateSelectedElement,!0),document.body.style.cursor="pointer"):(document.removeEventListener("mousemove",this.handleMouseMove),document.removeEventListener("click",this.handleClick,!0),document.removeEventListener("mouseleave",this.handleMouseLeave),window.removeEventListener("resize",this.recalculateSelectedElement),window.removeEventListener("scroll",this.recalculateSelectedElement,!0),this.hoverHighlighter?.remove(),this.hoverLabel?.remove(),this.selectedHighlighter?.remove(),this.selectedLabel?.remove(),this.hoverHighlighter=null,this.hoverLabel=null,this.selectedHighlighter=null,this.selectedLabel=null,document.body.style.cursor="",this.selectedElement=null)}};if(typeof window<"u")try{window.REPLIT_BEACON_VERSION||(window.REPLIT_BEACON_VERSION=F,new R)}catch(e){console.error("[replit-beacon] Failed to initialize:",e)}})();
</script>
  <style type="text/css" data-vite-dev-id="/home/runner/workspace/client/src/index.css">*, ::before, ::after {
  --tw-border-spacing-x: 0;
  --tw-border-spacing-y: 0;
  --tw-translate-x: 0;
  --tw-translate-y: 0;
  --tw-rotate: 0;
  --tw-skew-x: 0;
  --tw-skew-y: 0;
  --tw-scale-x: 1;
  --tw-scale-y: 1;
  --tw-pan-x:  ;
  --tw-pan-y:  ;
  --tw-pinch-zoom:  ;
  --tw-scroll-snap-strictness: proximity;
  --tw-gradient-from-position:  ;
  --tw-gradient-via-position:  ;
  --tw-gradient-to-position:  ;
  --tw-ordinal:  ;
  --tw-slashed-zero:  ;
  --tw-numeric-figure:  ;
  --tw-numeric-spacing:  ;
  --tw-numeric-fraction:  ;
  --tw-ring-inset:  ;
  --tw-ring-offset-width: 0px;
  --tw-ring-offset-color: #fff;
  --tw-ring-color: rgb(59 130 246 / 0.5);
  --tw-ring-offset-shadow: 0 0 #0000;
  --tw-ring-shadow: 0 0 #0000;
  --tw-shadow: 0 0 #0000;
  --tw-shadow-colored: 0 0 #0000;
  --tw-blur:  ;
  --tw-brightness:  ;
  --tw-contrast:  ;
  --tw-grayscale:  ;
  --tw-hue-rotate:  ;
  --tw-invert:  ;
  --tw-saturate:  ;
  --tw-sepia:  ;
  --tw-drop-shadow:  ;
  --tw-backdrop-blur:  ;
  --tw-backdrop-brightness:  ;
  --tw-backdrop-contrast:  ;
  --tw-backdrop-grayscale:  ;
  --tw-backdrop-hue-rotate:  ;
  --tw-backdrop-invert:  ;
  --tw-backdrop-opacity:  ;
  --tw-backdrop-saturate:  ;
  --tw-backdrop-sepia:  ;
  --tw-contain-size:  ;
  --tw-contain-layout:  ;
  --tw-contain-paint:  ;
  --tw-contain-style:  ;
}

::backdrop {
  --tw-border-spacing-x: 0;
  --tw-border-spacing-y: 0;
  --tw-translate-x: 0;
  --tw-translate-y: 0;
  --tw-rotate: 0;
  --tw-skew-x: 0;
  --tw-skew-y: 0;
  --tw-scale-x: 1;
  --tw-scale-y: 1;
  --tw-pan-x:  ;
  --tw-pan-y:  ;
  --tw-pinch-zoom:  ;
  --tw-scroll-snap-strictness: proximity;
  --tw-gradient-from-position:  ;
  --tw-gradient-via-position:  ;
  --tw-gradient-to-position:  ;
  --tw-ordinal:  ;
  --tw-slashed-zero:  ;
  --tw-numeric-figure:  ;
  --tw-numeric-spacing:  ;
  --tw-numeric-fraction:  ;
  --tw-ring-inset:  ;
  --tw-ring-offset-width: 0px;
  --tw-ring-offset-color: #fff;
  --tw-ring-color: rgb(59 130 246 / 0.5);
  --tw-ring-offset-shadow: 0 0 #0000;
  --tw-ring-shadow: 0 0 #0000;
  --tw-shadow: 0 0 #0000;
  --tw-shadow-colored: 0 0 #0000;
  --tw-blur:  ;
  --tw-brightness:  ;
  --tw-contrast:  ;
  --tw-grayscale:  ;
  --tw-hue-rotate:  ;
  --tw-invert:  ;
  --tw-saturate:  ;
  --tw-sepia:  ;
  --tw-drop-shadow:  ;
  --tw-backdrop-blur:  ;
  --tw-backdrop-brightness:  ;
  --tw-backdrop-contrast:  ;
  --tw-backdrop-grayscale:  ;
  --tw-backdrop-hue-rotate:  ;
  --tw-backdrop-invert:  ;
  --tw-backdrop-opacity:  ;
  --tw-backdrop-saturate:  ;
  --tw-backdrop-sepia:  ;
  --tw-contain-size:  ;
  --tw-contain-layout:  ;
  --tw-contain-paint:  ;
  --tw-contain-style:  ;
}/*
! tailwindcss v3.4.14 | MIT License | https://tailwindcss.com
*//*
1. Prevent padding and border from affecting element width. (https://github.com/mozdevs/cssremedy/issues/4)
2. Allow adding a border to an element by just adding a border-width. (https://github.com/tailwindcss/tailwindcss/pull/116)
*/

*,
::before,
::after {
  box-sizing: border-box; /* 1 */
  border-width: 0; /* 2 */
  border-style: solid; /* 2 */
  border-color: #e5e7eb; /* 2 */
}

::before,
::after {
  --tw-content: '';
}

/*
1. Use a consistent sensible line-height in all browsers.
2. Prevent adjustments of font size after orientation changes in iOS.
3. Use a more readable tab size.
4. Use the user's configured `sans` font-family by default.
5. Use the user's configured `sans` font-feature-settings by default.
6. Use the user's configured `sans` font-variation-settings by default.
7. Disable tap highlights on iOS
*/

html,
:host {
  line-height: 1.5; /* 1 */
  -webkit-text-size-adjust: 100%; /* 2 */
  -moz-tab-size: 4; /* 3 */
  -o-tab-size: 4;
     tab-size: 4; /* 3 */
  font-family: ui-sans-serif, system-ui, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji"; /* 4 */
  font-feature-settings: normal; /* 5 */
  font-variation-settings: normal; /* 6 */
  -webkit-tap-highlight-color: transparent; /* 7 */
}

/*
1. Remove the margin in all browsers.
2. Inherit line-height from `html` so users can set them as a class directly on the `html` element.
*/

body {
  margin: 0; /* 1 */
  line-height: inherit; /* 2 */
}

/*
1. Add the correct height in Firefox.
2. Correct the inheritance of border color in Firefox. (https://bugzilla.mozilla.org/show_bug.cgi?id=190655)
3. Ensure horizontal rules are visible by default.
*/

hr {
  height: 0; /* 1 */
  color: inherit; /* 2 */
  border-top-width: 1px; /* 3 */
}

/*
Add the correct text decoration in Chrome, Edge, and Safari.
*/

abbr:where([title]) {
  -webkit-text-decoration: underline dotted;
          text-decoration: underline dotted;
}

/*
Remove the default font size and weight for headings.
*/

h1,
h2,
h3,
h4,
h5,
h6 {
  font-size: inherit;
  font-weight: inherit;
}

/*
Reset links to optimize for opt-in styling instead of opt-out.
*/

a {
  color: inherit;
  text-decoration: inherit;
}

/*
Add the correct font weight in Edge and Safari.
*/

b,
strong {
  font-weight: bolder;
}

/*
1. Use the user's configured `mono` font-family by default.
2. Use the user's configured `mono` font-feature-settings by default.
3. Use the user's configured `mono` font-variation-settings by default.
4. Correct the odd `em` font sizing in all browsers.
*/

code,
kbd,
samp,
pre {
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; /* 1 */
  font-feature-settings: normal; /* 2 */
  font-variation-settings: normal; /* 3 */
  font-size: 1em; /* 4 */
}

/*
Add the correct font size in all browsers.
*/

small {
  font-size: 80%;
}

/*
Prevent `sub` and `sup` elements from affecting the line height in all browsers.
*/

sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}

sub {
  bottom: -0.25em;
}

sup {
  top: -0.5em;
}

/*
1. Remove text indentation from table contents in Chrome and Safari. (https://bugs.chromium.org/p/chromium/issues/detail?id=999088, https://bugs.webkit.org/show_bug.cgi?id=201297)
2. Correct table border color inheritance in all Chrome and Safari. (https://bugs.chromium.org/p/chromium/issues/detail?id=935729, https://bugs.webkit.org/show_bug.cgi?id=195016)
3. Remove gaps between table borders by default.
*/

table {
  text-indent: 0; /* 1 */
  border-color: inherit; /* 2 */
  border-collapse: collapse; /* 3 */
}

/*
1. Change the font styles in all browsers.
2. Remove the margin in Firefox and Safari.
3. Remove default padding in all browsers.
*/

button,
input,
optgroup,
select,
textarea {
  font-family: inherit; /* 1 */
  font-feature-settings: inherit; /* 1 */
  font-variation-settings: inherit; /* 1 */
  font-size: 100%; /* 1 */
  font-weight: inherit; /* 1 */
  line-height: inherit; /* 1 */
  letter-spacing: inherit; /* 1 */
  color: inherit; /* 1 */
  margin: 0; /* 2 */
  padding: 0; /* 3 */
}

/*
Remove the inheritance of text transform in Edge and Firefox.
*/

button,
select {
  text-transform: none;
}

/*
1. Correct the inability to style clickable types in iOS and Safari.
2. Remove default button styles.
*/

button,
input:where([type='button']),
input:where([type='reset']),
input:where([type='submit']) {
  -webkit-appearance: button; /* 1 */
  background-color: transparent; /* 2 */
  background-image: none; /* 2 */
}

/*
Use the modern Firefox focus style for all focusable elements.
*/

:-moz-focusring {
  outline: auto;
}

/*
Remove the additional `:invalid` styles in Firefox. (https://github.com/mozilla/gecko-dev/blob/2f9eacd9d3d995c937b4251a5557d95d494c9be1/layout/style/res/forms.css#L728-L737)
*/

:-moz-ui-invalid {
  box-shadow: none;
}

/*
Add the correct vertical alignment in Chrome and Firefox.
*/

progress {
  vertical-align: baseline;
}

/*
Correct the cursor style of increment and decrement buttons in Safari.
*/

::-webkit-inner-spin-button,
::-webkit-outer-spin-button {
  height: auto;
}

/*
1. Correct the odd appearance in Chrome and Safari.
2. Correct the outline style in Safari.
*/

[type='search'] {
  -webkit-appearance: textfield; /* 1 */
  outline-offset: -2px; /* 2 */
}

/*
Remove the inner padding in Chrome and Safari on macOS.
*/

::-webkit-search-decoration {
  -webkit-appearance: none;
}

/*
1. Correct the inability to style clickable types in iOS and Safari.
2. Change font properties to `inherit` in Safari.
*/

::-webkit-file-upload-button {
  -webkit-appearance: button; /* 1 */
  font: inherit; /* 2 */
}

/*
Add the correct display in Chrome and Safari.
*/

summary {
  display: list-item;
}

/*
Removes the default spacing and border for appropriate elements.
*/

blockquote,
dl,
dd,
h1,
h2,
h3,
h4,
h5,
h6,
hr,
figure,
p,
pre {
  margin: 0;
}

fieldset {
  margin: 0;
  padding: 0;
}

legend {
  padding: 0;
}

ol,
ul,
menu {
  list-style: none;
  margin: 0;
  padding: 0;
}

/*
Reset default styling for dialogs.
*/
dialog {
  padding: 0;
}

/*
Prevent resizing textareas horizontally by default.
*/

textarea {
  resize: vertical;
}

/*
1. Reset the default placeholder opacity in Firefox. (https://github.com/tailwindlabs/tailwindcss/issues/3300)
2. Set the default placeholder color to the user's configured gray 400 color.
*/

input::-moz-placeholder, textarea::-moz-placeholder {
  opacity: 1; /* 1 */
  color: #9ca3af; /* 2 */
}

input::placeholder,
textarea::placeholder {
  opacity: 1; /* 1 */
  color: #9ca3af; /* 2 */
}

/*
Set the default cursor for buttons.
*/

button,
[role="button"] {
  cursor: pointer;
}

/*
Make sure disabled buttons don't get the pointer cursor.
*/
:disabled {
  cursor: default;
}

/*
1. Make replaced elements `display: block` by default. (https://github.com/mozdevs/cssremedy/issues/14)
2. Add `vertical-align: middle` to align replaced elements more sensibly by default. (https://github.com/jensimmons/cssremedy/issues/14#issuecomment-634934210)
   This can trigger a poorly considered lint error in some tools but is included by design.
*/

img,
svg,
video,
canvas,
audio,
iframe,
embed,
object {
  display: block; /* 1 */
  vertical-align: middle; /* 2 */
}

/*
Constrain images and videos to the parent width and preserve their intrinsic aspect ratio. (https://github.com/mozdevs/cssremedy/issues/14)
*/

img,
video {
  max-width: 100%;
  height: auto;
}

/* Make elements with the HTML hidden attribute stay hidden by default */
[hidden]:where(:not([hidden="until-found"])) {
  display: none;
}
  * {
  border-color: hsl(var(--border));
}

  body {
  background-color: hsl(var(--background));
  font-family: ui-sans-serif, system-ui, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  color: hsl(var(--foreground));
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
    color: #343A40;
    font-family: 'Inter', sans-serif;
}
.container {
  width: 100%;
}
@media (min-width: 640px) {

  .container {
    max-width: 640px;
  }
}
@media (min-width: 768px) {

  .container {
    max-width: 768px;
  }
}
@media (min-width: 1024px) {

  .container {
    max-width: 1024px;
  }
}
@media (min-width: 1280px) {

  .container {
    max-width: 1280px;
  }
}
@media (min-width: 1536px) {

  .container {
    max-width: 1536px;
  }
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}
.pointer-events-none {
  pointer-events: none;
}
.pointer-events-auto {
  pointer-events: auto;
}
.visible {
  visibility: visible;
}
.invisible {
  visibility: hidden;
}
.fixed {
  position: fixed;
}
.absolute {
  position: absolute;
}
.relative {
  position: relative;
}
.sticky {
  position: sticky;
}
.inset-0 {
  inset: 0px;
}
.inset-x-0 {
  left: 0px;
  right: 0px;
}
.inset-y-0 {
  top: 0px;
  bottom: 0px;
}
.-bottom-12 {
  bottom: -3rem;
}
.-left-12 {
  left: -3rem;
}
.-right-12 {
  right: -3rem;
}
.-top-12 {
  top: -3rem;
}
.bottom-0 {
  bottom: 0px;
}
.left-0 {
  left: 0px;
}
.left-1 {
  left: 0.25rem;
}
.left-1\/2 {
  left: 50%;
}
.left-2 {
  left: 0.5rem;
}
.left-\[50\%\] {
  left: 50%;
}
.right-0 {
  right: 0px;
}
.right-1 {
  right: 0.25rem;
}
.right-2 {
  right: 0.5rem;
}
.right-3 {
  right: 0.75rem;
}
.right-4 {
  right: 1rem;
}
.top-0 {
  top: 0px;
}
.top-1\.5 {
  top: 0.375rem;
}
.top-1\/2 {
  top: 50%;
}
.top-2 {
  top: 0.5rem;
}
.top-2\.5 {
  top: 0.625rem;
}
.top-3\.5 {
  top: 0.875rem;
}
.top-4 {
  top: 1rem;
}
.top-\[1px\] {
  top: 1px;
}
.top-\[50\%\] {
  top: 50%;
}
.top-\[60\%\] {
  top: 60%;
}
.top-full {
  top: 100%;
}
.z-10 {
  z-index: 10;
}
.z-20 {
  z-index: 20;
}
.z-40 {
  z-index: 40;
}
.z-50 {
  z-index: 50;
}
.z-\[100\] {
  z-index: 100;
}
.z-\[1\] {
  z-index: 1;
}
.col-span-full {
  grid-column: 1 / -1;
}
.-mx-1 {
  margin-left: -0.25rem;
  margin-right: -0.25rem;
}
.mx-2 {
  margin-left: 0.5rem;
  margin-right: 0.5rem;
}
.mx-3\.5 {
  margin-left: 0.875rem;
  margin-right: 0.875rem;
}
.mx-4 {
  margin-left: 1rem;
  margin-right: 1rem;
}
.mx-auto {
  margin-left: auto;
  margin-right: auto;
}
.my-0\.5 {
  margin-top: 0.125rem;
  margin-bottom: 0.125rem;
}
.my-1 {
  margin-top: 0.25rem;
  margin-bottom: 0.25rem;
}
.my-4 {
  margin-top: 1rem;
  margin-bottom: 1rem;
}
.-ml-4 {
  margin-left: -1rem;
}
.-mt-4 {
  margin-top: -1rem;
}
.mb-0\.5 {
  margin-bottom: 0.125rem;
}
.mb-1 {
  margin-bottom: 0.25rem;
}
.mb-16 {
  margin-bottom: 4rem;
}
.mb-2 {
  margin-bottom: 0.5rem;
}
.mb-20 {
  margin-bottom: 5rem;
}
.mb-3 {
  margin-bottom: 0.75rem;
}
.mb-4 {
  margin-bottom: 1rem;
}
.mb-6 {
  margin-bottom: 1.5rem;
}
.mb-8 {
  margin-bottom: 2rem;
}
.ml-1 {
  margin-left: 0.25rem;
}
.ml-2 {
  margin-left: 0.5rem;
}
.ml-auto {
  margin-left: auto;
}
.mr-1 {
  margin-right: 0.25rem;
}
.mr-2 {
  margin-right: 0.5rem;
}
.mr-3 {
  margin-right: 0.75rem;
}
.mt-0\.5 {
  margin-top: 0.125rem;
}
.mt-1 {
  margin-top: 0.25rem;
}
.mt-1\.5 {
  margin-top: 0.375rem;
}
.mt-2 {
  margin-top: 0.5rem;
}
.mt-24 {
  margin-top: 6rem;
}
.mt-3 {
  margin-top: 0.75rem;
}
.mt-4 {
  margin-top: 1rem;
}
.mt-6 {
  margin-top: 1.5rem;
}
.mt-auto {
  margin-top: auto;
}
.block {
  display: block;
}
.inline-block {
  display: inline-block;
}
.flex {
  display: flex;
}
.inline-flex {
  display: inline-flex;
}
.table {
  display: table;
}
.grid {
  display: grid;
}
.hidden {
  display: none;
}
.aspect-square {
  aspect-ratio: 1 / 1;
}
.aspect-video {
  aspect-ratio: 16 / 9;
}
.size-4 {
  width: 1rem;
  height: 1rem;
}
.h-1\.5 {
  height: 0.375rem;
}
.h-10 {
  height: 2.5rem;
}
.h-11 {
  height: 2.75rem;
}
.h-12 {
  height: 3rem;
}
.h-16 {
  height: 4rem;
}
.h-2 {
  height: 0.5rem;
}
.h-2\.5 {
  height: 0.625rem;
}
.h-20 {
  height: 5rem;
}
.h-3 {
  height: 0.75rem;
}
.h-3\.5 {
  height: 0.875rem;
}
.h-4 {
  height: 1rem;
}
.h-48 {
  height: 12rem;
}
.h-5 {
  height: 1.25rem;
}
.h-6 {
  height: 1.5rem;
}
.h-7 {
  height: 1.75rem;
}
.h-8 {
  height: 2rem;
}
.h-9 {
  height: 2.25rem;
}
.h-\[1px\] {
  height: 1px;
}
.h-\[300px\] {
  height: 300px;
}
.h-\[var\(--radix-navigation-menu-viewport-height\)\] {
  height: var(--radix-navigation-menu-viewport-height);
}
.h-\[var\(--radix-select-trigger-height\)\] {
  height: var(--radix-select-trigger-height);
}
.h-auto {
  height: auto;
}
.h-full {
  height: 100%;
}
.h-px {
  height: 1px;
}
.h-svh {
  height: 100svh;
}
.max-h-96 {
  max-height: 24rem;
}
.max-h-\[300px\] {
  max-height: 300px;
}
.max-h-\[90vh\] {
  max-height: 90vh;
}
.max-h-screen {
  max-height: 100vh;
}
.min-h-0 {
  min-height: 0px;
}
.min-h-\[80px\] {
  min-height: 80px;
}
.min-h-\[80vh\] {
  min-height: 80vh;
}
.min-h-screen {
  min-height: 100vh;
}
.min-h-svh {
  min-height: 100svh;
}
.w-0 {
  width: 0px;
}
.w-1 {
  width: 0.25rem;
}
.w-1\/2 {
  width: 50%;
}
.w-10 {
  width: 2.5rem;
}
.w-11 {
  width: 2.75rem;
}
.w-12 {
  width: 3rem;
}
.w-16 {
  width: 4rem;
}
.w-2 {
  width: 0.5rem;
}
.w-2\.5 {
  width: 0.625rem;
}
.w-2\/3 {
  width: 66.666667%;
}
.w-20 {
  width: 5rem;
}
.w-24 {
  width: 6rem;
}
.w-3 {
  width: 0.75rem;
}
.w-3\.5 {
  width: 0.875rem;
}
.w-3\/4 {
  width: 75%;
}
.w-4 {
  width: 1rem;
}
.w-48 {
  width: 12rem;
}
.w-5 {
  width: 1.25rem;
}
.w-6 {
  width: 1.5rem;
}
.w-64 {
  width: 16rem;
}
.w-7 {
  width: 1.75rem;
}
.w-72 {
  width: 18rem;
}
.w-8 {
  width: 2rem;
}
.w-9 {
  width: 2.25rem;
}
.w-\[--sidebar-width\] {
  width: var(--sidebar-width);
}
.w-\[100px\] {
  width: 100px;
}
.w-\[1px\] {
  width: 1px;
}
.w-auto {
  width: auto;
}
.w-full {
  width: 100%;
}
.w-max {
  width: -moz-max-content;
  width: max-content;
}
.w-px {
  width: 1px;
}
.min-w-0 {
  min-width: 0px;
}
.min-w-5 {
  min-width: 1.25rem;
}
.min-w-\[12rem\] {
  min-width: 12rem;
}
.min-w-\[8rem\] {
  min-width: 8rem;
}
.min-w-\[var\(--radix-select-trigger-width\)\] {
  min-width: var(--radix-select-trigger-width);
}
.min-w-max {
  min-width: -moz-max-content;
  min-width: max-content;
}
.max-w-\[--skeleton-width\] {
  max-width: var(--skeleton-width);
}
.max-w-\[95\%\] {
  max-width: 95%;
}
.max-w-lg {
  max-width: 32rem;
}
.max-w-max {
  max-width: -moz-max-content;
  max-width: max-content;
}
.max-w-md {
  max-width: 28rem;
}
.flex-1 {
  flex: 1 1 0%;
}
.flex-shrink-0 {
  flex-shrink: 0;
}
.shrink-0 {
  flex-shrink: 0;
}
.flex-grow {
  flex-grow: 1;
}
.grow {
  flex-grow: 1;
}
.grow-0 {
  flex-grow: 0;
}
.basis-full {
  flex-basis: 100%;
}
.caption-bottom {
  caption-side: bottom;
}
.border-collapse {
  border-collapse: collapse;
}
.-translate-x-1\/2 {
  --tw-translate-x: -50%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.-translate-x-px {
  --tw-translate-x: -1px;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.-translate-y-1\/2 {
  --tw-translate-y: -50%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.translate-x-\[-50\%\] {
  --tw-translate-x: -50%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.translate-x-px {
  --tw-translate-x: 1px;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.translate-y-\[-50\%\] {
  --tw-translate-y: -50%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.rotate-45 {
  --tw-rotate: 45deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.rotate-90 {
  --tw-rotate: 90deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.transform {
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
@keyframes pulse {

  50% {
    opacity: .5;
  }
}
.animate-pulse {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}
@keyframes spin {

  to {
    transform: rotate(360deg);
  }
}
.animate-spin {
  animation: spin 1s linear infinite;
}
.cursor-default {
  cursor: default;
}
.cursor-pointer {
  cursor: pointer;
}
.touch-none {
  touch-action: none;
}
.select-none {
  -webkit-user-select: none;
     -moz-user-select: none;
          user-select: none;
}
.list-none {
  list-style-type: none;
}
.appearance-none {
  -webkit-appearance: none;
     -moz-appearance: none;
          appearance: none;
}
.grid-cols-1 {
  grid-template-columns: repeat(1, minmax(0, 1fr));
}
.grid-cols-2 {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}
.grid-cols-4 {
  grid-template-columns: repeat(4, minmax(0, 1fr));
}
.flex-row {
  flex-direction: row;
}
.flex-col {
  flex-direction: column;
}
.flex-col-reverse {
  flex-direction: column-reverse;
}
.flex-wrap {
  flex-wrap: wrap;
}
.items-start {
  align-items: flex-start;
}
.items-end {
  align-items: flex-end;
}
.items-center {
  align-items: center;
}
.items-stretch {
  align-items: stretch;
}
.justify-start {
  justify-content: flex-start;
}
.justify-end {
  justify-content: flex-end;
}
.justify-center {
  justify-content: center;
}
.justify-between {
  justify-content: space-between;
}
.justify-around {
  justify-content: space-around;
}
.gap-1 {
  gap: 0.25rem;
}
.gap-1\.5 {
  gap: 0.375rem;
}
.gap-2 {
  gap: 0.5rem;
}
.gap-3 {
  gap: 0.75rem;
}
.gap-4 {
  gap: 1rem;
}
.gap-6 {
  gap: 1.5rem;
}
.space-x-1 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-x-reverse: 0;
  margin-right: calc(0.25rem * var(--tw-space-x-reverse));
  margin-left: calc(0.25rem * calc(1 - var(--tw-space-x-reverse)));
}
.space-x-2 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-x-reverse: 0;
  margin-right: calc(0.5rem * var(--tw-space-x-reverse));
  margin-left: calc(0.5rem * calc(1 - var(--tw-space-x-reverse)));
}
.space-x-3 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-x-reverse: 0;
  margin-right: calc(0.75rem * var(--tw-space-x-reverse));
  margin-left: calc(0.75rem * calc(1 - var(--tw-space-x-reverse)));
}
.space-x-4 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-x-reverse: 0;
  margin-right: calc(1rem * var(--tw-space-x-reverse));
  margin-left: calc(1rem * calc(1 - var(--tw-space-x-reverse)));
}
.space-x-6 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-x-reverse: 0;
  margin-right: calc(1.5rem * var(--tw-space-x-reverse));
  margin-left: calc(1.5rem * calc(1 - var(--tw-space-x-reverse)));
}
.space-y-1 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-y-reverse: 0;
  margin-top: calc(0.25rem * calc(1 - var(--tw-space-y-reverse)));
  margin-bottom: calc(0.25rem * var(--tw-space-y-reverse));
}
.space-y-1\.5 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-y-reverse: 0;
  margin-top: calc(0.375rem * calc(1 - var(--tw-space-y-reverse)));
  margin-bottom: calc(0.375rem * var(--tw-space-y-reverse));
}
.space-y-2 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-y-reverse: 0;
  margin-top: calc(0.5rem * calc(1 - var(--tw-space-y-reverse)));
  margin-bottom: calc(0.5rem * var(--tw-space-y-reverse));
}
.space-y-4 > :not([hidden]) ~ :not([hidden]) {
  --tw-space-y-reverse: 0;
  margin-top: calc(1rem * calc(1 - var(--tw-space-y-reverse)));
  margin-bottom: calc(1rem * var(--tw-space-y-reverse));
}
.self-start {
  align-self: flex-start;
}
.overflow-auto {
  overflow: auto;
}
.overflow-hidden {
  overflow: hidden;
}
.overflow-x-auto {
  overflow-x: auto;
}
.overflow-y-auto {
  overflow-y: auto;
}
.overflow-x-hidden {
  overflow-x: hidden;
}
.truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
.whitespace-nowrap {
  white-space: nowrap;
}
.break-words {
  overflow-wrap: break-word;
}
.break-all {
  word-break: break-all;
}
.rounded-\[2px\] {
  border-radius: 2px;
}
.rounded-\[inherit\] {
  border-radius: inherit;
}
.rounded-full {
  border-radius: 9999px;
}
.rounded-lg {
  border-radius: var(--radius);
}
.rounded-md {
  border-radius: calc(var(--radius) - 2px);
}
.rounded-sm {
  border-radius: calc(var(--radius) - 4px);
}
.rounded-xl {
  border-radius: 0.75rem;
}
.rounded-l-lg {
  border-top-left-radius: var(--radius);
  border-bottom-left-radius: var(--radius);
}
.rounded-r-lg {
  border-top-right-radius: var(--radius);
  border-bottom-right-radius: var(--radius);
}
.rounded-t-\[10px\] {
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}
.rounded-tl-sm {
  border-top-left-radius: calc(var(--radius) - 4px);
}
.border {
  border-width: 1px;
}
.border-2 {
  border-width: 2px;
}
.border-\[1\.5px\] {
  border-width: 1.5px;
}
.border-y {
  border-top-width: 1px;
  border-bottom-width: 1px;
}
.border-b {
  border-bottom-width: 1px;
}
.border-b-2 {
  border-bottom-width: 2px;
}
.border-l {
  border-left-width: 1px;
}
.border-r {
  border-right-width: 1px;
}
.border-t {
  border-top-width: 1px;
}
.border-t-2 {
  border-top-width: 2px;
}
.border-dashed {
  border-style: dashed;
}
.border-\[\#2D6A4F\] {
  --tw-border-opacity: 1;
  border-color: rgb(45 106 79 / var(--tw-border-opacity));
}
.border-\[\#CED4DA\] {
  --tw-border-opacity: 1;
  border-color: rgb(206 212 218 / var(--tw-border-opacity));
}
.border-\[--color-border\] {
  border-color: var(--color-border);
}
.border-border {
  border-color: hsl(var(--border));
}
.border-border\/50 {
  border-color: hsl(var(--border) / 0.5);
}
.border-destructive {
  border-color: hsl(var(--destructive));
}
.border-destructive\/50 {
  border-color: hsl(var(--destructive) / 0.5);
}
.border-input {
  border-color: hsl(var(--input));
}
.border-primary {
  border-color: hsl(var(--primary));
}
.border-sidebar-border {
  border-color: hsl(var(--sidebar-border));
}
.border-transparent {
  border-color: transparent;
}
.border-l-transparent {
  border-left-color: transparent;
}
.border-t-transparent {
  border-top-color: transparent;
}
.bg-\[\#2D6A4F\] {
  --tw-bg-opacity: 1;
  background-color: rgb(45 106 79 / var(--tw-bg-opacity));
}
.bg-\[\#343A40\]\/50 {
  background-color: rgb(52 58 64 / 0.5);
}
.bg-\[\#495057\] {
  --tw-bg-opacity: 1;
  background-color: rgb(73 80 87 / var(--tw-bg-opacity));
}
.bg-\[\#52B788\] {
  --tw-bg-opacity: 1;
  background-color: rgb(82 183 136 / var(--tw-bg-opacity));
}
.bg-\[\#52B788\]\/10 {
  background-color: rgb(82 183 136 / 0.1);
}
.bg-\[\#52B788\]\/20 {
  background-color: rgb(82 183 136 / 0.2);
}
.bg-\[\#9C6644\] {
  --tw-bg-opacity: 1;
  background-color: rgb(156 102 68 / var(--tw-bg-opacity));
}
.bg-\[\#CED4DA\] {
  --tw-bg-opacity: 1;
  background-color: rgb(206 212 218 / var(--tw-bg-opacity));
}
.bg-\[\#E9C46A\] {
  --tw-bg-opacity: 1;
  background-color: rgb(233 196 106 / var(--tw-bg-opacity));
}
.bg-\[\#E9ECEF\] {
  --tw-bg-opacity: 1;
  background-color: rgb(233 236 239 / var(--tw-bg-opacity));
}
.bg-\[\#F8FAF9\] {
  --tw-bg-opacity: 1;
  background-color: rgb(248 250 249 / var(--tw-bg-opacity));
}
.bg-\[--color-bg\] {
  background-color: var(--color-bg);
}
.bg-accent {
  background-color: hsl(var(--accent));
}
.bg-background {
  background-color: hsl(var(--background));
}
.bg-black\/80 {
  background-color: rgb(0 0 0 / 0.8);
}
.bg-border {
  background-color: hsl(var(--border));
}
.bg-card {
  background-color: hsl(var(--card));
}
.bg-destructive {
  background-color: hsl(var(--destructive));
}
.bg-foreground {
  background-color: hsl(var(--foreground));
}
.bg-muted {
  background-color: hsl(var(--muted));
}
.bg-muted\/50 {
  background-color: hsl(var(--muted) / 0.5);
}
.bg-popover {
  background-color: hsl(var(--popover));
}
.bg-primary {
  background-color: hsl(var(--primary));
}
.bg-primary\/10 {
  background-color: hsl(var(--primary) / 0.1);
}
.bg-secondary {
  background-color: hsl(var(--secondary));
}
.bg-sidebar {
  background-color: hsl(var(--sidebar-background));
}
.bg-sidebar-border {
  background-color: hsl(var(--sidebar-border));
}
.bg-transparent {
  background-color: transparent;
}
.bg-white {
  --tw-bg-opacity: 1;
  background-color: rgb(255 255 255 / var(--tw-bg-opacity));
}
.bg-white\/80 {
  background-color: rgb(255 255 255 / 0.8);
}
.fill-current {
  fill: currentColor;
}
.object-cover {
  -o-object-fit: cover;
     object-fit: cover;
}
.p-0 {
  padding: 0px;
}
.p-1 {
  padding: 0.25rem;
}
.p-2 {
  padding: 0.5rem;
}
.p-3 {
  padding: 0.75rem;
}
.p-4 {
  padding: 1rem;
}
.p-5 {
  padding: 1.25rem;
}
.p-6 {
  padding: 1.5rem;
}
.p-8 {
  padding: 2rem;
}
.p-\[1px\] {
  padding: 1px;
}
.px-1 {
  padding-left: 0.25rem;
  padding-right: 0.25rem;
}
.px-2 {
  padding-left: 0.5rem;
  padding-right: 0.5rem;
}
.px-2\.5 {
  padding-left: 0.625rem;
  padding-right: 0.625rem;
}
.px-3 {
  padding-left: 0.75rem;
  padding-right: 0.75rem;
}
.px-4 {
  padding-left: 1rem;
  padding-right: 1rem;
}
.px-5 {
  padding-left: 1.25rem;
  padding-right: 1.25rem;
}
.px-6 {
  padding-left: 1.5rem;
  padding-right: 1.5rem;
}
.px-8 {
  padding-left: 2rem;
  padding-right: 2rem;
}
.py-0\.5 {
  padding-top: 0.125rem;
  padding-bottom: 0.125rem;
}
.py-1 {
  padding-top: 0.25rem;
  padding-bottom: 0.25rem;
}
.py-1\.5 {
  padding-top: 0.375rem;
  padding-bottom: 0.375rem;
}
.py-12 {
  padding-top: 3rem;
  padding-bottom: 3rem;
}
.py-2 {
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
}
.py-2\.5 {
  padding-top: 0.625rem;
  padding-bottom: 0.625rem;
}
.py-3 {
  padding-top: 0.75rem;
  padding-bottom: 0.75rem;
}
.py-4 {
  padding-top: 1rem;
  padding-bottom: 1rem;
}
.py-6 {
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
}
.py-8 {
  padding-top: 2rem;
  padding-bottom: 2rem;
}
.pb-16 {
  padding-bottom: 4rem;
}
.pb-2 {
  padding-bottom: 0.5rem;
}
.pb-3 {
  padding-bottom: 0.75rem;
}
.pb-4 {
  padding-bottom: 1rem;
}
.pl-2\.5 {
  padding-left: 0.625rem;
}
.pl-4 {
  padding-left: 1rem;
}
.pl-8 {
  padding-left: 2rem;
}
.pr-10 {
  padding-right: 2.5rem;
}
.pr-2 {
  padding-right: 0.5rem;
}
.pr-2\.5 {
  padding-right: 0.625rem;
}
.pr-8 {
  padding-right: 2rem;
}
.pt-0 {
  padding-top: 0px;
}
.pt-1 {
  padding-top: 0.25rem;
}
.pt-3 {
  padding-top: 0.75rem;
}
.pt-4 {
  padding-top: 1rem;
}
.pt-6 {
  padding-top: 1.5rem;
}
.text-left {
  text-align: left;
}
.text-center {
  text-align: center;
}
.align-middle {
  vertical-align: middle;
}
.font-mono {
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
}
.text-2xl {
  font-size: 1.5rem;
  line-height: 2rem;
}
.text-3xl {
  font-size: 1.875rem;
  line-height: 2.25rem;
}
.text-\[0\.8rem\] {
  font-size: 0.8rem;
}
.text-\[10px\] {
  font-size: 10px;
}
.text-base {
  font-size: 1rem;
  line-height: 1.5rem;
}
.text-lg {
  font-size: 1.125rem;
  line-height: 1.75rem;
}
.text-sm {
  font-size: 0.875rem;
  line-height: 1.25rem;
}
.text-xl {
  font-size: 1.25rem;
  line-height: 1.75rem;
}
.text-xs {
  font-size: 0.75rem;
  line-height: 1rem;
}
.font-bold {
  font-weight: 700;
}
.font-medium {
  font-weight: 500;
}
.font-normal {
  font-weight: 400;
}
.font-semibold {
  font-weight: 600;
}
.tabular-nums {
  --tw-numeric-spacing: tabular-nums;
  font-variant-numeric: var(--tw-ordinal) var(--tw-slashed-zero) var(--tw-numeric-figure) var(--tw-numeric-spacing) var(--tw-numeric-fraction);
}
.leading-none {
  line-height: 1;
}
.tracking-tight {
  letter-spacing: -0.025em;
}
.tracking-widest {
  letter-spacing: 0.1em;
}
.text-\[\#1B4332\] {
  --tw-text-opacity: 1;
  color: rgb(27 67 50 / var(--tw-text-opacity));
}
.text-\[\#2D6A4F\] {
  --tw-text-opacity: 1;
  color: rgb(45 106 79 / var(--tw-text-opacity));
}
.text-\[\#343A40\] {
  --tw-text-opacity: 1;
  color: rgb(52 58 64 / var(--tw-text-opacity));
}
.text-\[\#40916C\] {
  --tw-text-opacity: 1;
  color: rgb(64 145 108 / var(--tw-text-opacity));
}
.text-\[\#495057\] {
  --tw-text-opacity: 1;
  color: rgb(73 80 87 / var(--tw-text-opacity));
}
.text-\[\#495057\]\/60 {
  color: rgb(73 80 87 / 0.6);
}
.text-\[\#9C6644\] {
  --tw-text-opacity: 1;
  color: rgb(156 102 68 / var(--tw-text-opacity));
}
.text-\[\#E9C46A\] {
  --tw-text-opacity: 1;
  color: rgb(233 196 106 / var(--tw-text-opacity));
}
.text-accent-foreground {
  color: hsl(var(--accent-foreground));
}
.text-card-foreground {
  color: hsl(var(--card-foreground));
}
.text-current {
  color: currentColor;
}
.text-destructive {
  color: hsl(var(--destructive));
}
.text-destructive-foreground {
  color: hsl(var(--destructive-foreground));
}
.text-foreground {
  color: hsl(var(--foreground));
}
.text-foreground\/50 {
  color: hsl(var(--foreground) / 0.5);
}
.text-green-500 {
  --tw-text-opacity: 1;
  color: rgb(34 197 94 / var(--tw-text-opacity));
}
.text-green-600 {
  --tw-text-opacity: 1;
  color: rgb(22 163 74 / var(--tw-text-opacity));
}
.text-muted-foreground {
  color: hsl(var(--muted-foreground));
}
.text-popover-foreground {
  color: hsl(var(--popover-foreground));
}
.text-primary {
  color: hsl(var(--primary));
}
.text-primary-foreground {
  color: hsl(var(--primary-foreground));
}
.text-red-500 {
  --tw-text-opacity: 1;
  color: rgb(239 68 68 / var(--tw-text-opacity));
}
.text-secondary-foreground {
  color: hsl(var(--secondary-foreground));
}
.text-sidebar-foreground {
  color: hsl(var(--sidebar-foreground));
}
.text-sidebar-foreground\/70 {
  color: hsl(var(--sidebar-foreground) / 0.7);
}
.text-white {
  --tw-text-opacity: 1;
  color: rgb(255 255 255 / var(--tw-text-opacity));
}
.line-through {
  text-decoration-line: line-through;
}
.underline-offset-4 {
  text-underline-offset: 4px;
}
.accent-\[\#2D6A4F\] {
  accent-color: #2D6A4F;
}
.accent-\[\#52B788\] {
  accent-color: #52B788;
}
.opacity-0 {
  opacity: 0;
}
.opacity-50 {
  opacity: 0.5;
}
.opacity-60 {
  opacity: 0.6;
}
.opacity-70 {
  opacity: 0.7;
}
.opacity-90 {
  opacity: 0.9;
}
.shadow-\[0_0_0_1px_hsl\(var\(--sidebar-border\)\)\] {
  --tw-shadow: 0 0 0 1px hsl(var(--sidebar-border));
  --tw-shadow-colored: 0 0 0 1px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
.shadow-\[0_2px_8px_rgba\(0\2c 0\2c 0\2c 0\.05\)\] {
  --tw-shadow: 0 2px 8px rgba(0,0,0,0.05);
  --tw-shadow-colored: 0 2px 8px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
.shadow-lg {
  --tw-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
  --tw-shadow-colored: 0 10px 15px -3px var(--tw-shadow-color), 0 4px 6px -4px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
.shadow-md {
  --tw-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
  --tw-shadow-colored: 0 4px 6px -1px var(--tw-shadow-color), 0 2px 4px -2px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
.shadow-none {
  --tw-shadow: 0 0 #0000;
  --tw-shadow-colored: 0 0 #0000;
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
.shadow-sm {
  --tw-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05);
  --tw-shadow-colored: 0 1px 2px 0 var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
.shadow-xl {
  --tw-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
  --tw-shadow-colored: 0 20px 25px -5px var(--tw-shadow-color), 0 8px 10px -6px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}
.outline-none {
  outline: 2px solid transparent;
  outline-offset: 2px;
}
.outline {
  outline-style: solid;
}
.ring-0 {
  --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
  --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(0px + var(--tw-ring-offset-width)) var(--tw-ring-color);
  box-shadow: var(--tw-ring-offset-shadow), var(--tw-ring-shadow), var(--tw-shadow, 0 0 #0000);
}
.ring-2 {
  --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
  --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(2px + var(--tw-ring-offset-width)) var(--tw-ring-color);
  box-shadow: var(--tw-ring-offset-shadow), var(--tw-ring-shadow), var(--tw-shadow, 0 0 #0000);
}
.ring-ring {
  --tw-ring-color: hsl(var(--ring));
}
.ring-sidebar-ring {
  --tw-ring-color: hsl(var(--sidebar-ring));
}
.ring-offset-background {
  --tw-ring-offset-color: hsl(var(--background));
}
.filter {
  filter: var(--tw-blur) var(--tw-brightness) var(--tw-contrast) var(--tw-grayscale) var(--tw-hue-rotate) var(--tw-invert) var(--tw-saturate) var(--tw-sepia) var(--tw-drop-shadow);
}
.transition {
  transition-property: color, background-color, border-color, text-decoration-color, fill, stroke, opacity, box-shadow, transform, filter, -webkit-backdrop-filter;
  transition-property: color, background-color, border-color, text-decoration-color, fill, stroke, opacity, box-shadow, transform, filter, backdrop-filter;
  transition-property: color, background-color, border-color, text-decoration-color, fill, stroke, opacity, box-shadow, transform, filter, backdrop-filter, -webkit-backdrop-filter;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-\[left\2c right\2c width\] {
  transition-property: left,right,width;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-\[margin\2c opa\] {
  transition-property: margin,opa;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-\[width\2c height\2c padding\] {
  transition-property: width,height,padding;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-\[width\] {
  transition-property: width;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-all {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-colors {
  transition-property: color, background-color, border-color, text-decoration-color, fill, stroke;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-opacity {
  transition-property: opacity;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.transition-transform {
  transition-property: transform;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
.duration-1000 {
  transition-duration: 1000ms;
}
.duration-200 {
  transition-duration: 200ms;
}
.ease-in-out {
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}
.ease-linear {
  transition-timing-function: linear;
}
@keyframes enter {

  from {
    opacity: var(--tw-enter-opacity, 1);
    transform: translate3d(var(--tw-enter-translate-x, 0), var(--tw-enter-translate-y, 0), 0) scale3d(var(--tw-enter-scale, 1), var(--tw-enter-scale, 1), var(--tw-enter-scale, 1)) rotate(var(--tw-enter-rotate, 0));
  }
}
@keyframes exit {

  to {
    opacity: var(--tw-exit-opacity, 1);
    transform: translate3d(var(--tw-exit-translate-x, 0), var(--tw-exit-translate-y, 0), 0) scale3d(var(--tw-exit-scale, 1), var(--tw-exit-scale, 1), var(--tw-exit-scale, 1)) rotate(var(--tw-exit-rotate, 0));
  }
}
.animate-in {
  animation-name: enter;
  animation-duration: 150ms;
  --tw-enter-opacity: initial;
  --tw-enter-scale: initial;
  --tw-enter-rotate: initial;
  --tw-enter-translate-x: initial;
  --tw-enter-translate-y: initial;
}
.fade-in-0 {
  --tw-enter-opacity: 0;
}
.fade-in-80 {
  --tw-enter-opacity: 0.8;
}
.zoom-in-95 {
  --tw-enter-scale: .95;
}
.duration-1000 {
  animation-duration: 1000ms;
}
.duration-200 {
  animation-duration: 200ms;
}
.ease-in-out {
  animation-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}
.ease-linear {
  animation-timing-function: linear;
}

.transition-all {
  transition: all 0.3s ease;
}

.meal-card:hover {
  transform: translateY(-3px);
}

.meal-image {
  height: 160px;
  background-size: cover;
  background-position: center;
}

/* Animation for the leaf */
@keyframes float {
  0% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-10px) rotate(5deg); }
  100% { transform: translateY(0px) rotate(0deg); }
}

.float-animation {
  animation: float 4s ease-in-out infinite;
}

.progress-ring {
  transform: rotate(-90deg);
}

.progress-ring__circle {
  transition: stroke-dashoffset 0.35s;
  transform-origin: 50% 50%;
}

.file\:border-0::file-selector-button {
  border-width: 0px;
}

.file\:bg-transparent::file-selector-button {
  background-color: transparent;
}

.file\:text-sm::file-selector-button {
  font-size: 0.875rem;
  line-height: 1.25rem;
}

.file\:font-medium::file-selector-button {
  font-weight: 500;
}

.file\:text-foreground::file-selector-button {
  color: hsl(var(--foreground));
}

.placeholder\:text-muted-foreground::-moz-placeholder {
  color: hsl(var(--muted-foreground));
}

.placeholder\:text-muted-foreground::placeholder {
  color: hsl(var(--muted-foreground));
}

.after\:absolute::after {
  content: var(--tw-content);
  position: absolute;
}

.after\:-inset-2::after {
  content: var(--tw-content);
  inset: -0.5rem;
}

.after\:inset-y-0::after {
  content: var(--tw-content);
  top: 0px;
  bottom: 0px;
}

.after\:left-1\/2::after {
  content: var(--tw-content);
  left: 50%;
}

.after\:left-\[2px\]::after {
  content: var(--tw-content);
  left: 2px;
}

.after\:top-\[2px\]::after {
  content: var(--tw-content);
  top: 2px;
}

.after\:h-4::after {
  content: var(--tw-content);
  height: 1rem;
}

.after\:w-1::after {
  content: var(--tw-content);
  width: 0.25rem;
}

.after\:w-4::after {
  content: var(--tw-content);
  width: 1rem;
}

.after\:w-\[2px\]::after {
  content: var(--tw-content);
  width: 2px;
}

.after\:-translate-x-1\/2::after {
  content: var(--tw-content);
  --tw-translate-x: -50%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.after\:rounded-full::after {
  content: var(--tw-content);
  border-radius: 9999px;
}

.after\:bg-white::after {
  content: var(--tw-content);
  --tw-bg-opacity: 1;
  background-color: rgb(255 255 255 / var(--tw-bg-opacity));
}

.after\:transition-all::after {
  content: var(--tw-content);
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}

.after\:content-\[\'\'\]::after {
  --tw-content: '';
  content: var(--tw-content);
}

.first\:rounded-l-md:first-child {
  border-top-left-radius: calc(var(--radius) - 2px);
  border-bottom-left-radius: calc(var(--radius) - 2px);
}

.first\:border-l:first-child {
  border-left-width: 1px;
}

.last\:rounded-r-md:last-child {
  border-top-right-radius: calc(var(--radius) - 2px);
  border-bottom-right-radius: calc(var(--radius) - 2px);
}

.focus-within\:relative:focus-within {
  position: relative;
}

.focus-within\:z-20:focus-within {
  z-index: 20;
}

.hover\:border-\[\#2D6A4F\]:hover {
  --tw-border-opacity: 1;
  border-color: rgb(45 106 79 / var(--tw-border-opacity));
}

.hover\:bg-\[\#1B4332\]:hover {
  --tw-bg-opacity: 1;
  background-color: rgb(27 67 50 / var(--tw-bg-opacity));
}

.hover\:bg-\[\#2D6A4F\]:hover {
  --tw-bg-opacity: 1;
  background-color: rgb(45 106 79 / var(--tw-bg-opacity));
}

.hover\:bg-\[\#CED4DA\]:hover {
  --tw-bg-opacity: 1;
  background-color: rgb(206 212 218 / var(--tw-bg-opacity));
}

.hover\:bg-\[\#F8FAF9\]:hover {
  --tw-bg-opacity: 1;
  background-color: rgb(248 250 249 / var(--tw-bg-opacity));
}

.hover\:bg-accent:hover {
  background-color: hsl(var(--accent));
}

.hover\:bg-destructive\/80:hover {
  background-color: hsl(var(--destructive) / 0.8);
}

.hover\:bg-destructive\/90:hover {
  background-color: hsl(var(--destructive) / 0.9);
}

.hover\:bg-muted:hover {
  background-color: hsl(var(--muted));
}

.hover\:bg-muted\/50:hover {
  background-color: hsl(var(--muted) / 0.5);
}

.hover\:bg-primary:hover {
  background-color: hsl(var(--primary));
}

.hover\:bg-primary\/80:hover {
  background-color: hsl(var(--primary) / 0.8);
}

.hover\:bg-primary\/90:hover {
  background-color: hsl(var(--primary) / 0.9);
}

.hover\:bg-secondary:hover {
  background-color: hsl(var(--secondary));
}

.hover\:bg-secondary\/80:hover {
  background-color: hsl(var(--secondary) / 0.8);
}

.hover\:bg-sidebar-accent:hover {
  background-color: hsl(var(--sidebar-accent));
}

.hover\:bg-white:hover {
  --tw-bg-opacity: 1;
  background-color: rgb(255 255 255 / var(--tw-bg-opacity));
}

.hover\:text-\[\#1B4332\]:hover {
  --tw-text-opacity: 1;
  color: rgb(27 67 50 / var(--tw-text-opacity));
}

.hover\:text-\[\#2D6A4F\]:hover {
  --tw-text-opacity: 1;
  color: rgb(45 106 79 / var(--tw-text-opacity));
}

.hover\:text-accent-foreground:hover {
  color: hsl(var(--accent-foreground));
}

.hover\:text-foreground:hover {
  color: hsl(var(--foreground));
}

.hover\:text-muted-foreground:hover {
  color: hsl(var(--muted-foreground));
}

.hover\:text-primary:hover {
  color: hsl(var(--primary));
}

.hover\:text-primary-foreground:hover {
  color: hsl(var(--primary-foreground));
}

.hover\:text-sidebar-accent-foreground:hover {
  color: hsl(var(--sidebar-accent-foreground));
}

.hover\:text-white:hover {
  --tw-text-opacity: 1;
  color: rgb(255 255 255 / var(--tw-text-opacity));
}

.hover\:underline:hover {
  text-decoration-line: underline;
}

.hover\:opacity-100:hover {
  opacity: 1;
}

.hover\:shadow-\[0_0_0_1px_hsl\(var\(--sidebar-accent\)\)\]:hover {
  --tw-shadow: 0 0 0 1px hsl(var(--sidebar-accent));
  --tw-shadow-colored: 0 0 0 1px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}

.hover\:shadow-md:hover {
  --tw-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
  --tw-shadow-colored: 0 4px 6px -1px var(--tw-shadow-color), 0 2px 4px -2px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}

.hover\:after\:bg-sidebar-border:hover::after {
  content: var(--tw-content);
  background-color: hsl(var(--sidebar-border));
}

.focus\:border-transparent:focus {
  border-color: transparent;
}

.focus\:bg-accent:focus {
  background-color: hsl(var(--accent));
}

.focus\:bg-primary:focus {
  background-color: hsl(var(--primary));
}

.focus\:text-accent-foreground:focus {
  color: hsl(var(--accent-foreground));
}

.focus\:text-primary-foreground:focus {
  color: hsl(var(--primary-foreground));
}

.focus\:opacity-100:focus {
  opacity: 1;
}

.focus\:outline-none:focus {
  outline: 2px solid transparent;
  outline-offset: 2px;
}

.focus\:ring-2:focus {
  --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
  --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(2px + var(--tw-ring-offset-width)) var(--tw-ring-color);
  box-shadow: var(--tw-ring-offset-shadow), var(--tw-ring-shadow), var(--tw-shadow, 0 0 #0000);
}

.focus\:ring-\[\#52B788\]:focus {
  --tw-ring-opacity: 1;
  --tw-ring-color: rgb(82 183 136 / var(--tw-ring-opacity));
}

.focus\:ring-ring:focus {
  --tw-ring-color: hsl(var(--ring));
}

.focus\:ring-offset-2:focus {
  --tw-ring-offset-width: 2px;
}

.focus-visible\:outline-none:focus-visible {
  outline: 2px solid transparent;
  outline-offset: 2px;
}

.focus-visible\:ring-1:focus-visible {
  --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
  --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(1px + var(--tw-ring-offset-width)) var(--tw-ring-color);
  box-shadow: var(--tw-ring-offset-shadow), var(--tw-ring-shadow), var(--tw-shadow, 0 0 #0000);
}

.focus-visible\:ring-2:focus-visible {
  --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
  --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(2px + var(--tw-ring-offset-width)) var(--tw-ring-color);
  box-shadow: var(--tw-ring-offset-shadow), var(--tw-ring-shadow), var(--tw-shadow, 0 0 #0000);
}

.focus-visible\:ring-ring:focus-visible {
  --tw-ring-color: hsl(var(--ring));
}

.focus-visible\:ring-sidebar-ring:focus-visible {
  --tw-ring-color: hsl(var(--sidebar-ring));
}

.focus-visible\:ring-offset-1:focus-visible {
  --tw-ring-offset-width: 1px;
}

.focus-visible\:ring-offset-2:focus-visible {
  --tw-ring-offset-width: 2px;
}

.focus-visible\:ring-offset-background:focus-visible {
  --tw-ring-offset-color: hsl(var(--background));
}

.active\:bg-sidebar-accent:active {
  background-color: hsl(var(--sidebar-accent));
}

.active\:text-sidebar-accent-foreground:active {
  color: hsl(var(--sidebar-accent-foreground));
}

.disabled\:pointer-events-none:disabled {
  pointer-events: none;
}

.disabled\:cursor-not-allowed:disabled {
  cursor: not-allowed;
}

.disabled\:opacity-50:disabled {
  opacity: 0.5;
}

.group\/menu-item:focus-within .group-focus-within\/menu-item\:opacity-100 {
  opacity: 1;
}

.group\/menu-item:hover .group-hover\/menu-item\:opacity-100 {
  opacity: 1;
}

.group:hover .group-hover\:opacity-100 {
  opacity: 1;
}

.group.destructive .group-\[\.destructive\]\:border-muted\/40 {
  border-color: hsl(var(--muted) / 0.4);
}

.group.destructive .group-\[\.destructive\]\:text-red-300 {
  --tw-text-opacity: 1;
  color: rgb(252 165 165 / var(--tw-text-opacity));
}

.group.destructive .group-\[\.destructive\]\:hover\:border-destructive\/30:hover {
  border-color: hsl(var(--destructive) / 0.3);
}

.group.destructive .group-\[\.destructive\]\:hover\:bg-destructive:hover {
  background-color: hsl(var(--destructive));
}

.group.destructive .group-\[\.destructive\]\:hover\:text-destructive-foreground:hover {
  color: hsl(var(--destructive-foreground));
}

.group.destructive .group-\[\.destructive\]\:hover\:text-red-50:hover {
  --tw-text-opacity: 1;
  color: rgb(254 242 242 / var(--tw-text-opacity));
}

.group.destructive .group-\[\.destructive\]\:focus\:ring-destructive:focus {
  --tw-ring-color: hsl(var(--destructive));
}

.group.destructive .group-\[\.destructive\]\:focus\:ring-red-400:focus {
  --tw-ring-opacity: 1;
  --tw-ring-color: rgb(248 113 113 / var(--tw-ring-opacity));
}

.group.destructive .group-\[\.destructive\]\:focus\:ring-offset-red-600:focus {
  --tw-ring-offset-color: #dc2626;
}

.peer:checked ~ .peer-checked\:bg-\[\#2D6A4F\] {
  --tw-bg-opacity: 1;
  background-color: rgb(45 106 79 / var(--tw-bg-opacity));
}

.peer:checked ~ .peer-checked\:after\:translate-x-full::after {
  content: var(--tw-content);
  --tw-translate-x: 100%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.peer\/menu-button:hover ~ .peer-hover\/menu-button\:text-sidebar-accent-foreground {
  color: hsl(var(--sidebar-accent-foreground));
}

.peer:focus ~ .peer-focus\:outline-none {
  outline: 2px solid transparent;
  outline-offset: 2px;
}

.peer:disabled ~ .peer-disabled\:cursor-not-allowed {
  cursor: not-allowed;
}

.peer:disabled ~ .peer-disabled\:opacity-70 {
  opacity: 0.7;
}

.has-\[\[data-variant\=inset\]\]\:bg-sidebar:has([data-variant=inset]) {
  background-color: hsl(var(--sidebar-background));
}

.has-\[\:disabled\]\:opacity-50:has(:disabled) {
  opacity: 0.5;
}

.group\/menu-item:has([data-sidebar=menu-action]) .group-has-\[\[data-sidebar\=menu-action\]\]\/menu-item\:pr-8 {
  padding-right: 2rem;
}

.aria-disabled\:pointer-events-none[aria-disabled="true"] {
  pointer-events: none;
}

.aria-disabled\:opacity-50[aria-disabled="true"] {
  opacity: 0.5;
}

.aria-selected\:bg-accent[aria-selected="true"] {
  background-color: hsl(var(--accent));
}

.aria-selected\:bg-accent\/50[aria-selected="true"] {
  background-color: hsl(var(--accent) / 0.5);
}

.aria-selected\:text-accent-foreground[aria-selected="true"] {
  color: hsl(var(--accent-foreground));
}

.aria-selected\:text-muted-foreground[aria-selected="true"] {
  color: hsl(var(--muted-foreground));
}

.aria-selected\:opacity-100[aria-selected="true"] {
  opacity: 1;
}

.aria-selected\:opacity-30[aria-selected="true"] {
  opacity: 0.3;
}

.data-\[disabled\=true\]\:pointer-events-none[data-disabled="true"] {
  pointer-events: none;
}

.data-\[disabled\]\:pointer-events-none[data-disabled] {
  pointer-events: none;
}

.data-\[panel-group-direction\=vertical\]\:h-px[data-panel-group-direction="vertical"] {
  height: 1px;
}

.data-\[panel-group-direction\=vertical\]\:w-full[data-panel-group-direction="vertical"] {
  width: 100%;
}

.data-\[side\=bottom\]\:translate-y-1[data-side="bottom"] {
  --tw-translate-y: 0.25rem;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[side\=left\]\:-translate-x-1[data-side="left"] {
  --tw-translate-x: -0.25rem;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[side\=right\]\:translate-x-1[data-side="right"] {
  --tw-translate-x: 0.25rem;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[side\=top\]\:-translate-y-1[data-side="top"] {
  --tw-translate-y: -0.25rem;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[state\=checked\]\:translate-x-5[data-state="checked"] {
  --tw-translate-x: 1.25rem;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[state\=unchecked\]\:translate-x-0[data-state="unchecked"] {
  --tw-translate-x: 0px;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[swipe\=cancel\]\:translate-x-0[data-swipe="cancel"] {
  --tw-translate-x: 0px;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[swipe\=end\]\:translate-x-\[var\(--radix-toast-swipe-end-x\)\][data-swipe="end"] {
  --tw-translate-x: var(--radix-toast-swipe-end-x);
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[swipe\=move\]\:translate-x-\[var\(--radix-toast-swipe-move-x\)\][data-swipe="move"] {
  --tw-translate-x: var(--radix-toast-swipe-move-x);
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

@keyframes accordion-up {

  from {
    height: var(--radix-accordion-content-height);
  }

  to {
    height: 0;
  }
}

.data-\[state\=closed\]\:animate-accordion-up[data-state="closed"] {
  animation: accordion-up 0.2s ease-out;
}

@keyframes accordion-down {

  from {
    height: 0;
  }

  to {
    height: var(--radix-accordion-content-height);
  }
}

.data-\[state\=open\]\:animate-accordion-down[data-state="open"] {
  animation: accordion-down 0.2s ease-out;
}

.data-\[panel-group-direction\=vertical\]\:flex-col[data-panel-group-direction="vertical"] {
  flex-direction: column;
}

.data-\[active\=true\]\:bg-sidebar-accent[data-active="true"] {
  background-color: hsl(var(--sidebar-accent));
}

.data-\[active\]\:bg-accent\/50[data-active] {
  background-color: hsl(var(--accent) / 0.5);
}

.data-\[selected\=\'true\'\]\:bg-accent[data-selected='true'] {
  background-color: hsl(var(--accent));
}

.data-\[state\=active\]\:bg-background[data-state="active"] {
  background-color: hsl(var(--background));
}

.data-\[state\=checked\]\:bg-primary[data-state="checked"] {
  background-color: hsl(var(--primary));
}

.data-\[state\=on\]\:bg-accent[data-state="on"] {
  background-color: hsl(var(--accent));
}

.data-\[state\=open\]\:bg-accent[data-state="open"] {
  background-color: hsl(var(--accent));
}

.data-\[state\=open\]\:bg-accent\/50[data-state="open"] {
  background-color: hsl(var(--accent) / 0.5);
}

.data-\[state\=open\]\:bg-secondary[data-state="open"] {
  background-color: hsl(var(--secondary));
}

.data-\[state\=selected\]\:bg-muted[data-state="selected"] {
  background-color: hsl(var(--muted));
}

.data-\[state\=unchecked\]\:bg-input[data-state="unchecked"] {
  background-color: hsl(var(--input));
}

.data-\[active\=true\]\:font-medium[data-active="true"] {
  font-weight: 500;
}

.data-\[active\=true\]\:text-sidebar-accent-foreground[data-active="true"] {
  color: hsl(var(--sidebar-accent-foreground));
}

.data-\[selected\=true\]\:text-accent-foreground[data-selected="true"] {
  color: hsl(var(--accent-foreground));
}

.data-\[state\=active\]\:text-foreground[data-state="active"] {
  color: hsl(var(--foreground));
}

.data-\[state\=checked\]\:text-primary-foreground[data-state="checked"] {
  color: hsl(var(--primary-foreground));
}

.data-\[state\=on\]\:text-accent-foreground[data-state="on"] {
  color: hsl(var(--accent-foreground));
}

.data-\[state\=open\]\:text-accent-foreground[data-state="open"] {
  color: hsl(var(--accent-foreground));
}

.data-\[state\=open\]\:text-muted-foreground[data-state="open"] {
  color: hsl(var(--muted-foreground));
}

.data-\[disabled\=true\]\:opacity-50[data-disabled="true"] {
  opacity: 0.5;
}

.data-\[disabled\]\:opacity-50[data-disabled] {
  opacity: 0.5;
}

.data-\[state\=open\]\:opacity-100[data-state="open"] {
  opacity: 1;
}

.data-\[state\=active\]\:shadow-sm[data-state="active"] {
  --tw-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05);
  --tw-shadow-colored: 0 1px 2px 0 var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}

.data-\[swipe\=move\]\:transition-none[data-swipe="move"] {
  transition-property: none;
}

.data-\[state\=closed\]\:duration-300[data-state="closed"] {
  transition-duration: 300ms;
}

.data-\[state\=open\]\:duration-500[data-state="open"] {
  transition-duration: 500ms;
}

.data-\[motion\^\=from-\]\:animate-in[data-motion^="from-"] {
  animation-name: enter;
  animation-duration: 150ms;
  --tw-enter-opacity: initial;
  --tw-enter-scale: initial;
  --tw-enter-rotate: initial;
  --tw-enter-translate-x: initial;
  --tw-enter-translate-y: initial;
}

.data-\[state\=open\]\:animate-in[data-state="open"] {
  animation-name: enter;
  animation-duration: 150ms;
  --tw-enter-opacity: initial;
  --tw-enter-scale: initial;
  --tw-enter-rotate: initial;
  --tw-enter-translate-x: initial;
  --tw-enter-translate-y: initial;
}

.data-\[state\=visible\]\:animate-in[data-state="visible"] {
  animation-name: enter;
  animation-duration: 150ms;
  --tw-enter-opacity: initial;
  --tw-enter-scale: initial;
  --tw-enter-rotate: initial;
  --tw-enter-translate-x: initial;
  --tw-enter-translate-y: initial;
}

.data-\[motion\^\=to-\]\:animate-out[data-motion^="to-"] {
  animation-name: exit;
  animation-duration: 150ms;
  --tw-exit-opacity: initial;
  --tw-exit-scale: initial;
  --tw-exit-rotate: initial;
  --tw-exit-translate-x: initial;
  --tw-exit-translate-y: initial;
}

.data-\[state\=closed\]\:animate-out[data-state="closed"] {
  animation-name: exit;
  animation-duration: 150ms;
  --tw-exit-opacity: initial;
  --tw-exit-scale: initial;
  --tw-exit-rotate: initial;
  --tw-exit-translate-x: initial;
  --tw-exit-translate-y: initial;
}

.data-\[state\=hidden\]\:animate-out[data-state="hidden"] {
  animation-name: exit;
  animation-duration: 150ms;
  --tw-exit-opacity: initial;
  --tw-exit-scale: initial;
  --tw-exit-rotate: initial;
  --tw-exit-translate-x: initial;
  --tw-exit-translate-y: initial;
}

.data-\[swipe\=end\]\:animate-out[data-swipe="end"] {
  animation-name: exit;
  animation-duration: 150ms;
  --tw-exit-opacity: initial;
  --tw-exit-scale: initial;
  --tw-exit-rotate: initial;
  --tw-exit-translate-x: initial;
  --tw-exit-translate-y: initial;
}

.data-\[motion\^\=from-\]\:fade-in[data-motion^="from-"] {
  --tw-enter-opacity: 0;
}

.data-\[motion\^\=to-\]\:fade-out[data-motion^="to-"] {
  --tw-exit-opacity: 0;
}

.data-\[state\=closed\]\:fade-out-0[data-state="closed"] {
  --tw-exit-opacity: 0;
}

.data-\[state\=closed\]\:fade-out-80[data-state="closed"] {
  --tw-exit-opacity: 0.8;
}

.data-\[state\=hidden\]\:fade-out[data-state="hidden"] {
  --tw-exit-opacity: 0;
}

.data-\[state\=open\]\:fade-in-0[data-state="open"] {
  --tw-enter-opacity: 0;
}

.data-\[state\=visible\]\:fade-in[data-state="visible"] {
  --tw-enter-opacity: 0;
}

.data-\[state\=closed\]\:zoom-out-95[data-state="closed"] {
  --tw-exit-scale: .95;
}

.data-\[state\=open\]\:zoom-in-90[data-state="open"] {
  --tw-enter-scale: .9;
}

.data-\[state\=open\]\:zoom-in-95[data-state="open"] {
  --tw-enter-scale: .95;
}

.data-\[motion\=from-end\]\:slide-in-from-right-52[data-motion="from-end"] {
  --tw-enter-translate-x: 13rem;
}

.data-\[motion\=from-start\]\:slide-in-from-left-52[data-motion="from-start"] {
  --tw-enter-translate-x: -13rem;
}

.data-\[motion\=to-end\]\:slide-out-to-right-52[data-motion="to-end"] {
  --tw-exit-translate-x: 13rem;
}

.data-\[motion\=to-start\]\:slide-out-to-left-52[data-motion="to-start"] {
  --tw-exit-translate-x: -13rem;
}

.data-\[side\=bottom\]\:slide-in-from-top-2[data-side="bottom"] {
  --tw-enter-translate-y: -0.5rem;
}

.data-\[side\=left\]\:slide-in-from-right-2[data-side="left"] {
  --tw-enter-translate-x: 0.5rem;
}

.data-\[side\=right\]\:slide-in-from-left-2[data-side="right"] {
  --tw-enter-translate-x: -0.5rem;
}

.data-\[side\=top\]\:slide-in-from-bottom-2[data-side="top"] {
  --tw-enter-translate-y: 0.5rem;
}

.data-\[state\=closed\]\:slide-out-to-bottom[data-state="closed"] {
  --tw-exit-translate-y: 100%;
}

.data-\[state\=closed\]\:slide-out-to-left[data-state="closed"] {
  --tw-exit-translate-x: -100%;
}

.data-\[state\=closed\]\:slide-out-to-left-1\/2[data-state="closed"] {
  --tw-exit-translate-x: -50%;
}

.data-\[state\=closed\]\:slide-out-to-right[data-state="closed"] {
  --tw-exit-translate-x: 100%;
}

.data-\[state\=closed\]\:slide-out-to-right-full[data-state="closed"] {
  --tw-exit-translate-x: 100%;
}

.data-\[state\=closed\]\:slide-out-to-top[data-state="closed"] {
  --tw-exit-translate-y: -100%;
}

.data-\[state\=closed\]\:slide-out-to-top-\[48\%\][data-state="closed"] {
  --tw-exit-translate-y: -48%;
}

.data-\[state\=open\]\:slide-in-from-bottom[data-state="open"] {
  --tw-enter-translate-y: 100%;
}

.data-\[state\=open\]\:slide-in-from-left[data-state="open"] {
  --tw-enter-translate-x: -100%;
}

.data-\[state\=open\]\:slide-in-from-left-1\/2[data-state="open"] {
  --tw-enter-translate-x: -50%;
}

.data-\[state\=open\]\:slide-in-from-right[data-state="open"] {
  --tw-enter-translate-x: 100%;
}

.data-\[state\=open\]\:slide-in-from-top[data-state="open"] {
  --tw-enter-translate-y: -100%;
}

.data-\[state\=open\]\:slide-in-from-top-\[48\%\][data-state="open"] {
  --tw-enter-translate-y: -48%;
}

.data-\[state\=open\]\:slide-in-from-top-full[data-state="open"] {
  --tw-enter-translate-y: -100%;
}

.data-\[state\=closed\]\:duration-300[data-state="closed"] {
  animation-duration: 300ms;
}

.data-\[state\=open\]\:duration-500[data-state="open"] {
  animation-duration: 500ms;
}

.data-\[panel-group-direction\=vertical\]\:after\:left-0[data-panel-group-direction="vertical"]::after {
  content: var(--tw-content);
  left: 0px;
}

.data-\[panel-group-direction\=vertical\]\:after\:h-1[data-panel-group-direction="vertical"]::after {
  content: var(--tw-content);
  height: 0.25rem;
}

.data-\[panel-group-direction\=vertical\]\:after\:w-full[data-panel-group-direction="vertical"]::after {
  content: var(--tw-content);
  width: 100%;
}

.data-\[panel-group-direction\=vertical\]\:after\:-translate-y-1\/2[data-panel-group-direction="vertical"]::after {
  content: var(--tw-content);
  --tw-translate-y: -50%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[panel-group-direction\=vertical\]\:after\:translate-x-0[data-panel-group-direction="vertical"]::after {
  content: var(--tw-content);
  --tw-translate-x: 0px;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.data-\[state\=open\]\:hover\:bg-sidebar-accent:hover[data-state="open"] {
  background-color: hsl(var(--sidebar-accent));
}

.data-\[state\=open\]\:hover\:text-sidebar-accent-foreground:hover[data-state="open"] {
  color: hsl(var(--sidebar-accent-foreground));
}

.group[data-collapsible="offcanvas"] .group-data-\[collapsible\=offcanvas\]\:left-\[calc\(var\(--sidebar-width\)\*-1\)\] {
  left: calc(var(--sidebar-width) * -1);
}

.group[data-collapsible="offcanvas"] .group-data-\[collapsible\=offcanvas\]\:right-\[calc\(var\(--sidebar-width\)\*-1\)\] {
  right: calc(var(--sidebar-width) * -1);
}

.group[data-side="left"] .group-data-\[side\=left\]\:-right-4 {
  right: -1rem;
}

.group[data-side="right"] .group-data-\[side\=right\]\:left-0 {
  left: 0px;
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:-mt-8 {
  margin-top: -2rem;
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:hidden {
  display: none;
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:\!size-8 {
  width: 2rem !important;
  height: 2rem !important;
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:w-\[--sidebar-width-icon\] {
  width: var(--sidebar-width-icon);
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:w-\[calc\(var\(--sidebar-width-icon\)_\+_theme\(spacing\.4\)\)\] {
  width: calc(var(--sidebar-width-icon) + 1rem);
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:w-\[calc\(var\(--sidebar-width-icon\)_\+_theme\(spacing\.4\)_\+2px\)\] {
  width: calc(var(--sidebar-width-icon) + 1rem + 2px);
}

.group[data-collapsible="offcanvas"] .group-data-\[collapsible\=offcanvas\]\:w-0 {
  width: 0px;
}

.group[data-collapsible="offcanvas"] .group-data-\[collapsible\=offcanvas\]\:translate-x-0 {
  --tw-translate-x: 0px;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.group[data-side="right"] .group-data-\[side\=right\]\:rotate-180 {
  --tw-rotate: 180deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.group[data-state="open"] .group-data-\[state\=open\]\:rotate-180 {
  --tw-rotate: 180deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:overflow-hidden {
  overflow: hidden;
}

.group[data-variant="floating"] .group-data-\[variant\=floating\]\:rounded-lg {
  border-radius: var(--radius);
}

.group[data-variant="floating"] .group-data-\[variant\=floating\]\:border {
  border-width: 1px;
}

.group[data-side="left"] .group-data-\[side\=left\]\:border-r {
  border-right-width: 1px;
}

.group[data-side="right"] .group-data-\[side\=right\]\:border-l {
  border-left-width: 1px;
}

.group[data-variant="floating"] .group-data-\[variant\=floating\]\:border-sidebar-border {
  border-color: hsl(var(--sidebar-border));
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:\!p-0 {
  padding: 0px !important;
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:\!p-2 {
  padding: 0.5rem !important;
}

.group[data-collapsible="icon"] .group-data-\[collapsible\=icon\]\:opacity-0 {
  opacity: 0;
}

.group[data-variant="floating"] .group-data-\[variant\=floating\]\:shadow {
  --tw-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
  --tw-shadow-colored: 0 1px 3px 0 var(--tw-shadow-color), 0 1px 2px -1px var(--tw-shadow-color);
  box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
}

.group[data-collapsible="offcanvas"] .group-data-\[collapsible\=offcanvas\]\:after\:left-full::after {
  content: var(--tw-content);
  left: 100%;
}

.group[data-collapsible="offcanvas"] .group-data-\[collapsible\=offcanvas\]\:hover\:bg-sidebar:hover {
  background-color: hsl(var(--sidebar-background));
}

.peer\/menu-button[data-size="default"] ~ .peer-data-\[size\=default\]\/menu-button\:top-1\.5 {
  top: 0.375rem;
}

.peer\/menu-button[data-size="lg"] ~ .peer-data-\[size\=lg\]\/menu-button\:top-2\.5 {
  top: 0.625rem;
}

.peer\/menu-button[data-size="sm"] ~ .peer-data-\[size\=sm\]\/menu-button\:top-1 {
  top: 0.25rem;
}

.peer[data-variant="inset"] ~ .peer-data-\[variant\=inset\]\:min-h-\[calc\(100svh-theme\(spacing\.4\)\)\] {
  min-height: calc(100svh - 1rem);
}

.peer\/menu-button[data-active="true"] ~ .peer-data-\[active\=true\]\/menu-button\:text-sidebar-accent-foreground {
  color: hsl(var(--sidebar-accent-foreground));
}

.dark\:border-destructive:is(.dark *) {
  border-color: hsl(var(--destructive));
}

@media (min-width: 640px) {

  .sm\:bottom-0 {
    bottom: 0px;
  }

  .sm\:right-0 {
    right: 0px;
  }

  .sm\:top-auto {
    top: auto;
  }

  .sm\:col-span-2 {
    grid-column: span 2 / span 2;
  }

  .sm\:col-span-3 {
    grid-column: span 3 / span 3;
  }

  .sm\:mb-2 {
    margin-bottom: 0.5rem;
  }

  .sm\:mb-8 {
    margin-bottom: 2rem;
  }

  .sm\:mt-0 {
    margin-top: 0px;
  }

  .sm\:flex {
    display: flex;
  }

  .sm\:h-24 {
    height: 6rem;
  }

  .sm\:h-6 {
    height: 1.5rem;
  }

  .sm\:h-\[400px\] {
    height: 400px;
  }

  .sm\:w-24 {
    width: 6rem;
  }

  .sm\:w-6 {
    width: 1.5rem;
  }

  .sm\:w-auto {
    width: auto;
  }

  .sm\:max-w-\[425px\] {
    max-width: 425px;
  }

  .sm\:max-w-sm {
    max-width: 24rem;
  }

  .sm\:grid-cols-2 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .sm\:grid-cols-3 {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }

  .sm\:grid-cols-4 {
    grid-template-columns: repeat(4, minmax(0, 1fr));
  }

  .sm\:flex-row {
    flex-direction: row;
  }

  .sm\:flex-col {
    flex-direction: column;
  }

  .sm\:flex-wrap {
    flex-wrap: wrap;
  }

  .sm\:items-center {
    align-items: center;
  }

  .sm\:justify-end {
    justify-content: flex-end;
  }

  .sm\:justify-between {
    justify-content: space-between;
  }

  .sm\:gap-2\.5 {
    gap: 0.625rem;
  }

  .sm\:gap-4 {
    gap: 1rem;
  }

  .sm\:space-x-2 > :not([hidden]) ~ :not([hidden]) {
    --tw-space-x-reverse: 0;
    margin-right: calc(0.5rem * var(--tw-space-x-reverse));
    margin-left: calc(0.5rem * calc(1 - var(--tw-space-x-reverse)));
  }

  .sm\:space-x-4 > :not([hidden]) ~ :not([hidden]) {
    --tw-space-x-reverse: 0;
    margin-right: calc(1rem * var(--tw-space-x-reverse));
    margin-left: calc(1rem * calc(1 - var(--tw-space-x-reverse)));
  }

  .sm\:space-y-0 > :not([hidden]) ~ :not([hidden]) {
    --tw-space-y-reverse: 0;
    margin-top: calc(0px * calc(1 - var(--tw-space-y-reverse)));
    margin-bottom: calc(0px * var(--tw-space-y-reverse));
  }

  .sm\:self-center {
    align-self: center;
  }

  .sm\:rounded-lg {
    border-radius: var(--radius);
  }

  .sm\:p-4 {
    padding: 1rem;
  }

  .sm\:p-6 {
    padding: 1.5rem;
  }

  .sm\:px-6 {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }

  .sm\:text-left {
    text-align: left;
  }

  .sm\:text-right {
    text-align: right;
  }

  .sm\:text-2xl {
    font-size: 1.5rem;
    line-height: 2rem;
  }

  .sm\:text-3xl {
    font-size: 1.875rem;
    line-height: 2.25rem;
  }

  .sm\:text-lg {
    font-size: 1.125rem;
    line-height: 1.75rem;
  }

  .sm\:text-xl {
    font-size: 1.25rem;
    line-height: 1.75rem;
  }

  .data-\[state\=open\]\:sm\:slide-in-from-bottom-full[data-state="open"] {
    --tw-enter-translate-y: 100%;
  }
}

@media (min-width: 768px) {

  .md\:absolute {
    position: absolute;
  }

  .md\:col-span-1 {
    grid-column: span 1 / span 1;
  }

  .md\:col-span-3 {
    grid-column: span 3 / span 3;
  }

  .md\:mb-0 {
    margin-bottom: 0px;
  }

  .md\:mb-10 {
    margin-bottom: 2.5rem;
  }

  .md\:mr-6 {
    margin-right: 1.5rem;
  }

  .md\:mt-0 {
    margin-top: 0px;
  }

  .md\:block {
    display: block;
  }

  .md\:flex {
    display: flex;
  }

  .md\:hidden {
    display: none;
  }

  .md\:w-1\/2 {
    width: 50%;
  }

  .md\:w-\[var\(--radix-navigation-menu-viewport-width\)\] {
    width: var(--radix-navigation-menu-viewport-width);
  }

  .md\:w-auto {
    width: auto;
  }

  .md\:max-w-\[420px\] {
    max-width: 420px;
  }

  .md\:grid-cols-2 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .md\:grid-cols-3 {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }

  .md\:grid-cols-4 {
    grid-template-columns: repeat(4, minmax(0, 1fr));
  }

  .md\:flex-row {
    flex-direction: row;
  }

  .md\:items-center {
    align-items: center;
  }

  .md\:justify-between {
    justify-content: space-between;
  }

  .md\:pb-0 {
    padding-bottom: 0px;
  }

  .md\:text-4xl {
    font-size: 2.25rem;
    line-height: 2.5rem;
  }

  .md\:opacity-0 {
    opacity: 0;
  }

  .after\:md\:hidden::after {
    content: var(--tw-content);
    display: none;
  }

  .peer[data-variant="inset"] ~ .md\:peer-data-\[variant\=inset\]\:m-2 {
    margin: 0.5rem;
  }

  .peer[data-state="collapsed"][data-variant="inset"] ~ .md\:peer-data-\[state\=collapsed\]\:peer-data-\[variant\=inset\]\:ml-2 {
    margin-left: 0.5rem;
  }

  .peer[data-variant="inset"] ~ .md\:peer-data-\[variant\=inset\]\:ml-0 {
    margin-left: 0px;
  }

  .peer[data-variant="inset"] ~ .md\:peer-data-\[variant\=inset\]\:rounded-xl {
    border-radius: 0.75rem;
  }

  .peer[data-variant="inset"] ~ .md\:peer-data-\[variant\=inset\]\:shadow {
    --tw-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
    --tw-shadow-colored: 0 1px 3px 0 var(--tw-shadow-color), 0 1px 2px -1px var(--tw-shadow-color);
    box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
  }
}

@media (min-width: 1024px) {

  .lg\:grid-cols-3 {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }
}

.\[\&\:has\(\[aria-selected\]\)\]\:bg-accent:has([aria-selected]) {
  background-color: hsl(var(--accent));
}

.first\:\[\&\:has\(\[aria-selected\]\)\]\:rounded-l-md:has([aria-selected]):first-child {
  border-top-left-radius: calc(var(--radius) - 2px);
  border-bottom-left-radius: calc(var(--radius) - 2px);
}

.last\:\[\&\:has\(\[aria-selected\]\)\]\:rounded-r-md:has([aria-selected]):last-child {
  border-top-right-radius: calc(var(--radius) - 2px);
  border-bottom-right-radius: calc(var(--radius) - 2px);
}

.\[\&\:has\(\[aria-selected\]\.day-outside\)\]\:bg-accent\/50:has([aria-selected].day-outside) {
  background-color: hsl(var(--accent) / 0.5);
}

.\[\&\:has\(\[aria-selected\]\.day-range-end\)\]\:rounded-r-md:has([aria-selected].day-range-end) {
  border-top-right-radius: calc(var(--radius) - 2px);
  border-bottom-right-radius: calc(var(--radius) - 2px);
}

.\[\&\:has\(\[role\=checkbox\]\)\]\:pr-0:has([role=checkbox]) {
  padding-right: 0px;
}

.\[\&\>button\]\:hidden>button {
  display: none;
}

.\[\&\>span\:last-child\]\:truncate>span:last-child {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.\[\&\>span\]\:line-clamp-1>span {
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 1;
}

.\[\&\>svg\+div\]\:translate-y-\[-3px\]>svg+div {
  --tw-translate-y: -3px;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.\[\&\>svg\]\:absolute>svg {
  position: absolute;
}

.\[\&\>svg\]\:left-4>svg {
  left: 1rem;
}

.\[\&\>svg\]\:top-4>svg {
  top: 1rem;
}

.\[\&\>svg\]\:size-4>svg {
  width: 1rem;
  height: 1rem;
}

.\[\&\>svg\]\:h-2\.5>svg {
  height: 0.625rem;
}

.\[\&\>svg\]\:h-3>svg {
  height: 0.75rem;
}

.\[\&\>svg\]\:h-3\.5>svg {
  height: 0.875rem;
}

.\[\&\>svg\]\:w-2\.5>svg {
  width: 0.625rem;
}

.\[\&\>svg\]\:w-3>svg {
  width: 0.75rem;
}

.\[\&\>svg\]\:w-3\.5>svg {
  width: 0.875rem;
}

.\[\&\>svg\]\:shrink-0>svg {
  flex-shrink: 0;
}

.\[\&\>svg\]\:text-destructive>svg {
  color: hsl(var(--destructive));
}

.\[\&\>svg\]\:text-foreground>svg {
  color: hsl(var(--foreground));
}

.\[\&\>svg\]\:text-muted-foreground>svg {
  color: hsl(var(--muted-foreground));
}

.\[\&\>svg\]\:text-sidebar-accent-foreground>svg {
  color: hsl(var(--sidebar-accent-foreground));
}

.\[\&\>svg\~\*\]\:pl-7>svg~* {
  padding-left: 1.75rem;
}

.\[\&\>tr\]\:last\:border-b-0:last-child>tr {
  border-bottom-width: 0px;
}

.\[\&\[data-panel-group-direction\=vertical\]\>div\]\:rotate-90[data-panel-group-direction=vertical]>div {
  --tw-rotate: 90deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.\[\&\[data-state\=open\]\>svg\]\:rotate-180[data-state=open]>svg {
  --tw-rotate: 180deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.\[\&_\.recharts-cartesian-axis-tick_text\]\:fill-muted-foreground .recharts-cartesian-axis-tick text {
  fill: hsl(var(--muted-foreground));
}

.\[\&_\.recharts-cartesian-grid_line\[stroke\=\'\#ccc\'\]\]\:stroke-border\/50 .recharts-cartesian-grid line[stroke='#ccc'] {
  stroke: hsl(var(--border) / 0.5);
}

.\[\&_\.recharts-curve\.recharts-tooltip-cursor\]\:stroke-border .recharts-curve.recharts-tooltip-cursor {
  stroke: hsl(var(--border));
}

.\[\&_\.recharts-dot\[stroke\=\'\#fff\'\]\]\:stroke-transparent .recharts-dot[stroke='#fff'] {
  stroke: transparent;
}

.\[\&_\.recharts-layer\]\:outline-none .recharts-layer {
  outline: 2px solid transparent;
  outline-offset: 2px;
}

.\[\&_\.recharts-polar-grid_\[stroke\=\'\#ccc\'\]\]\:stroke-border .recharts-polar-grid [stroke='#ccc'] {
  stroke: hsl(var(--border));
}

.\[\&_\.recharts-radial-bar-background-sector\]\:fill-muted .recharts-radial-bar-background-sector {
  fill: hsl(var(--muted));
}

.\[\&_\.recharts-rectangle\.recharts-tooltip-cursor\]\:fill-muted .recharts-rectangle.recharts-tooltip-cursor {
  fill: hsl(var(--muted));
}

.\[\&_\.recharts-reference-line_\[stroke\=\'\#ccc\'\]\]\:stroke-border .recharts-reference-line [stroke='#ccc'] {
  stroke: hsl(var(--border));
}

.\[\&_\.recharts-sector\[stroke\=\'\#fff\'\]\]\:stroke-transparent .recharts-sector[stroke='#fff'] {
  stroke: transparent;
}

.\[\&_\.recharts-sector\]\:outline-none .recharts-sector {
  outline: 2px solid transparent;
  outline-offset: 2px;
}

.\[\&_\.recharts-surface\]\:outline-none .recharts-surface {
  outline: 2px solid transparent;
  outline-offset: 2px;
}

.\[\&_\[cmdk-group-heading\]\]\:px-2 [cmdk-group-heading] {
  padding-left: 0.5rem;
  padding-right: 0.5rem;
}

.\[\&_\[cmdk-group-heading\]\]\:py-1\.5 [cmdk-group-heading] {
  padding-top: 0.375rem;
  padding-bottom: 0.375rem;
}

.\[\&_\[cmdk-group-heading\]\]\:text-xs [cmdk-group-heading] {
  font-size: 0.75rem;
  line-height: 1rem;
}

.\[\&_\[cmdk-group-heading\]\]\:font-medium [cmdk-group-heading] {
  font-weight: 500;
}

.\[\&_\[cmdk-group-heading\]\]\:text-muted-foreground [cmdk-group-heading] {
  color: hsl(var(--muted-foreground));
}

.\[\&_\[cmdk-group\]\:not\(\[hidden\]\)_\~\[cmdk-group\]\]\:pt-0 [cmdk-group]:not([hidden]) ~[cmdk-group] {
  padding-top: 0px;
}

.\[\&_\[cmdk-group\]\]\:px-2 [cmdk-group] {
  padding-left: 0.5rem;
  padding-right: 0.5rem;
}

.\[\&_\[cmdk-input-wrapper\]_svg\]\:h-5 [cmdk-input-wrapper] svg {
  height: 1.25rem;
}

.\[\&_\[cmdk-input-wrapper\]_svg\]\:w-5 [cmdk-input-wrapper] svg {
  width: 1.25rem;
}

.\[\&_\[cmdk-input\]\]\:h-12 [cmdk-input] {
  height: 3rem;
}

.\[\&_\[cmdk-item\]\]\:px-2 [cmdk-item] {
  padding-left: 0.5rem;
  padding-right: 0.5rem;
}

.\[\&_\[cmdk-item\]\]\:py-3 [cmdk-item] {
  padding-top: 0.75rem;
  padding-bottom: 0.75rem;
}

.\[\&_\[cmdk-item\]_svg\]\:h-5 [cmdk-item] svg {
  height: 1.25rem;
}

.\[\&_\[cmdk-item\]_svg\]\:w-5 [cmdk-item] svg {
  width: 1.25rem;
}

.\[\&_p\]\:leading-relaxed p {
  line-height: 1.625;
}

.\[\&_svg\]\:pointer-events-none svg {
  pointer-events: none;
}

.\[\&_svg\]\:size-4 svg {
  width: 1rem;
  height: 1rem;
}

.\[\&_svg\]\:shrink-0 svg {
  flex-shrink: 0;
}

.\[\&_tr\:last-child\]\:border-0 tr:last-child {
  border-width: 0px;
}

.\[\&_tr\]\:border-b tr {
  border-bottom-width: 1px;
}

[data-side=left][data-collapsible=offcanvas] .\[\[data-side\=left\]\[data-collapsible\=offcanvas\]_\&\]\:-right-2 {
  right: -0.5rem;
}

[data-side=left][data-state=collapsed] .\[\[data-side\=left\]\[data-state\=collapsed\]_\&\]\:cursor-e-resize {
  cursor: e-resize;
}

[data-side=left] .\[\[data-side\=left\]_\&\]\:cursor-w-resize {
  cursor: w-resize;
}

[data-side=right][data-collapsible=offcanvas] .\[\[data-side\=right\]\[data-collapsible\=offcanvas\]_\&\]\:-left-2 {
  left: -0.5rem;
}

[data-side=right][data-state=collapsed] .\[\[data-side\=right\]\[data-state\=collapsed\]_\&\]\:cursor-w-resize {
  cursor: w-resize;
}

[data-side=right] .\[\[data-side\=right\]_\&\]\:cursor-e-resize {
  cursor: e-resize;
}
</style></head>
  <body>
    <div id="root"><div data-replit-metadata="client/src/App.tsx:30:6" data-component-name="div" class="min-h-screen flex flex-col"><header data-replit-metadata="client/src/components/layout/Header.tsx:16:6" data-component-name="header" class="sticky top-0 z-40 bg-background shadow-sm"><div data-replit-metadata="client/src/components/layout/Header.tsx:17:8" data-component-name="div" class="container mx-auto px-4 py-3 flex justify-between items-center"><a data-replit-metadata="client/src/components/layout/Header.tsx:18:10" data-component-name="Link" href="/"><div data-replit-metadata="client/src/components/layout/Header.tsx:19:12" data-component-name="div" class="flex items-center cursor-pointer"><div data-replit-metadata="client/src/components/layout/Header.tsx:20:14" data-component-name="div" class="mr-2 text-primary"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-dollar-sign h-5 w-5 sm:h-6 sm:w-6" data-replit-metadata="client/src/components/layout/Header.tsx:21:16" data-component-name="CircleDollarSign"><circle cx="12" cy="12" r="10"></circle><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 18V6"></path></svg></div><h1 data-replit-metadata="client/src/components/layout/Header.tsx:23:14" data-component-name="h1" class="text-lg sm:text-xl font-semibold">BudgetKu</h1></div></a><nav data-replit-metadata="client/src/components/layout/Header.tsx:28:10" data-component-name="nav" class="hidden md:flex items-center space-x-6"><a data-replit-metadata="client/src/components/layout/Header.tsx:29:12" data-component-name="Link" href="/expenses"><div data-replit-metadata="client/src/components/layout/Header.tsx:30:14" data-component-name="div" class="flex items-center gap-1.5 transition-all cursor-pointer text-muted-foreground hover:text-primary"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-receipt h-4 w-4" data-replit-metadata="client/src/components/layout/Header.tsx:31:16" data-component-name="Receipt"><path d="M4 2v20l2-1 2 1 2-1 2 1 2-1 2 1 2-1 2 1V2l-2 1-2-1-2 1-2-1-2 1-2-1-2 1Z"></path><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 17.5v-11"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:32:16" data-component-name="span">Pengeluaran</span></div></a><a data-replit-metadata="client/src/components/layout/Header.tsx:35:12" data-component-name="Link" href="/budgets"><div data-replit-metadata="client/src/components/layout/Header.tsx:36:14" data-component-name="div" class="flex items-center gap-1.5 transition-all cursor-pointer text-muted-foreground hover:text-primary"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-dollar-sign h-4 w-4" data-replit-metadata="client/src/components/layout/Header.tsx:37:16" data-component-name="CircleDollarSign"><circle cx="12" cy="12" r="10"></circle><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 18V6"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:38:16" data-component-name="span">Budget</span></div></a><a data-replit-metadata="client/src/components/layout/Header.tsx:41:12" data-component-name="Link" href="/report"><div data-replit-metadata="client/src/components/layout/Header.tsx:42:14" data-component-name="div" class="flex items-center gap-1.5 transition-all cursor-pointer text-muted-foreground hover:text-primary"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-chart-column h-4 w-4" data-replit-metadata="client/src/components/layout/Header.tsx:43:16" data-component-name="BarChart3"><path d="M3 3v16a2 2 0 0 0 2 2h16"></path><path d="M18 17V9"></path><path d="M13 17V5"></path><path d="M8 17v-3"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:44:16" data-component-name="span">Laporan</span></div></a><a data-replit-metadata="client/src/components/layout/Header.tsx:47:12" data-component-name="Link" href="/profile"><div data-replit-metadata="client/src/components/layout/Header.tsx:48:14" data-component-name="div" class="flex items-center gap-1.5 transition-all cursor-pointer text-muted-foreground hover:text-primary"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-user h-5 w-5" data-replit-metadata="client/src/components/layout/Header.tsx:49:16" data-component-name="UserCircle"><circle cx="12" cy="12" r="10"></circle><circle cx="12" cy="10" r="3"></circle><path d="M7 20.662V19a2 2 0 0 1 2-2h6a2 2 0 0 1 2 2v1.662"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:50:16" data-component-name="span">Profil</span></div></a></nav><div data-replit-metadata="client/src/components/layout/Header.tsx:56:10" data-component-name="div" class="md:hidden flex items-center"><button data-replit-metadata="client/src/components/layout/Header.tsx:57:12" data-component-name="button" class="text-muted-foreground hover:text-primary" aria-label="Buka Menu"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-menu h-5 w-5" data-replit-metadata="client/src/components/layout/Header.tsx:62:60" data-component-name="Menu"><line x1="4" x2="20" y1="12" y2="12"></line><line x1="4" x2="20" y1="6" y2="6"></line><line x1="4" x2="20" y1="18" y2="18"></line></svg></button></div></div></header><nav data-replit-metadata="client/src/components/layout/Header.tsx:107:6" data-component-name="nav" class="md:hidden fixed bottom-0 left-0 right-0 z-50 bg-background border-t border-border px-2 py-1 flex justify-around items-center shadow-lg"><a data-replit-metadata="client/src/components/layout/Header.tsx:108:8" data-component-name="Link" href="/"><div data-replit-metadata="client/src/components/layout/Header.tsx:109:10" data-component-name="div" class="flex flex-col items-center py-1 px-2 text-primary"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-house h-5 w-5 mb-0.5" data-replit-metadata="client/src/components/layout/Header.tsx:110:12" data-component-name="Home"><path d="M15 21v-8a1 1 0 0 0-1-1h-4a1 1 0 0 0-1 1v8"></path><path d="M3 10a2 2 0 0 1 .709-1.528l7-5.999a2 2 0 0 1 2.582 0l7 5.999A2 2 0 0 1 21 10v9a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:111:12" data-component-name="span" class="text-[10px]">Beranda</span></div></a><a data-replit-metadata="client/src/components/layout/Header.tsx:114:8" data-component-name="Link" href="/expenses"><div data-replit-metadata="client/src/components/layout/Header.tsx:115:10" data-component-name="div" class="flex flex-col items-center py-1 px-2 text-muted-foreground"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-receipt h-5 w-5 mb-0.5" data-replit-metadata="client/src/components/layout/Header.tsx:116:12" data-component-name="Receipt"><path d="M4 2v20l2-1 2 1 2-1 2 1 2-1 2 1 2-1 2 1V2l-2 1-2-1-2 1-2-1-2 1-2-1-2 1Z"></path><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 17.5v-11"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:117:12" data-component-name="span" class="text-[10px]">Pengeluaran</span></div></a><a data-replit-metadata="client/src/components/layout/Header.tsx:120:8" data-component-name="Link" href="/budgets"><div data-replit-metadata="client/src/components/layout/Header.tsx:121:10" data-component-name="div" class="flex flex-col items-center py-1 px-2 text-muted-foreground"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-dollar-sign h-5 w-5 mb-0.5" data-replit-metadata="client/src/components/layout/Header.tsx:122:12" data-component-name="CircleDollarSign"><circle cx="12" cy="12" r="10"></circle><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 18V6"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:123:12" data-component-name="span" class="text-[10px]">Budget</span></div></a><a data-replit-metadata="client/src/components/layout/Header.tsx:126:8" data-component-name="Link" href="/report"><div data-replit-metadata="client/src/components/layout/Header.tsx:127:10" data-component-name="div" class="flex flex-col items-center py-1 px-2 text-muted-foreground"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-chart-column h-5 w-5 mb-0.5" data-replit-metadata="client/src/components/layout/Header.tsx:128:12" data-component-name="BarChart3"><path d="M3 3v16a2 2 0 0 0 2 2h16"></path><path d="M18 17V9"></path><path d="M13 17V5"></path><path d="M8 17v-3"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:129:12" data-component-name="span" class="text-[10px]">Laporan</span></div></a><a data-replit-metadata="client/src/components/layout/Header.tsx:132:8" data-component-name="Link" href="/profile"><div data-replit-metadata="client/src/components/layout/Header.tsx:133:10" data-component-name="div" class="flex flex-col items-center py-1 px-2 text-muted-foreground"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-user h-5 w-5 mb-0.5" data-replit-metadata="client/src/components/layout/Header.tsx:134:12" data-component-name="UserCircle"><circle cx="12" cy="12" r="10"></circle><circle cx="12" cy="10" r="3"></circle><path d="M7 20.662V19a2 2 0 0 1 2-2h6a2 2 0 0 1 2 2v1.662"></path></svg><span data-replit-metadata="client/src/components/layout/Header.tsx:135:12" data-component-name="span" class="text-[10px]">Profil</span></div></a></nav><div data-replit-metadata="client/src/App.tsx:32:8" data-component-name="div" class="flex-grow pb-16 md:pb-0"><main data-replit-metadata="client/src/pages/Home.tsx:36:4" data-component-name="main" class="container mx-auto px-4 py-6 mb-16"><section data-replit-metadata="client/src/pages/Home.tsx:38:6" data-component-name="section" class="mb-6 sm:mb-8 md:mb-10"><div data-replit-metadata="client/src/pages/Home.tsx:39:8" data-component-name="div" class="flex flex-col md:flex-row md:items-center md:justify-between"><div data-replit-metadata="client/src/pages/Home.tsx:40:10" data-component-name="div" class="mb-6 md:mb-0 md:w-1/2"><h1 data-replit-metadata="client/src/pages/Home.tsx:41:12" data-component-name="h1" class="text-2xl sm:text-3xl md:text-4xl font-bold mb-3">Kelola Keuanganmu<br data-replit-metadata="client/src/pages/Home.tsx:42:31" data-component-name="br">dengan Bijak</h1><p data-replit-metadata="client/src/pages/Home.tsx:44:12" data-component-name="p" class="text-base sm:text-lg text-muted-foreground mb-4">Pantau pengeluaran, atur budget, dan capai target finansial Anda dengan mudah.</p><div data-replit-metadata="client/src/pages/Home.tsx:47:12" data-component-name="div" class="grid grid-cols-2 gap-2 sm:flex sm:flex-wrap sm:gap-4"><button data-replit-metadata="client/src/pages/Home.tsx:48:14" data-component-name="Button" class="gap-2 whitespace-nowrap rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0 bg-primary text-primary-foreground hover:bg-primary/90 h-10 px-4 py-2 flex items-center justify-center"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-dollar-sign mr-2 h-4 w-4" data-replit-metadata="client/src/pages/Home.tsx:53:16" data-component-name="CircleDollarSign"><circle cx="12" cy="12" r="10"></circle><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 18V6"></path></svg>Atur Budget</button><button data-replit-metadata="client/src/pages/Home.tsx:56:14" data-component-name="Button" class="gap-2 whitespace-nowrap rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0 border border-input bg-background hover:bg-accent hover:text-accent-foreground h-10 px-4 py-2 flex items-center justify-center"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-arrow-down mr-2 h-4 w-4" data-replit-metadata="client/src/pages/Home.tsx:62:16" data-component-name="ArrowDownCircle"><circle cx="12" cy="12" r="10"></circle><path d="M12 8v8"></path><path d="m8 12 4 4 4-4"></path></svg>Catat Pengeluaran</button></div></div><div data-replit-metadata="client/src/pages/Home.tsx:69:10" data-component-name="div" class="md:w-1/2 mt-6 md:mt-0"><div data-replit-metadata="client/src/pages/Home.tsx:70:12" data-component-name="div" class="grid grid-cols-1 gap-3"><div data-replit-metadata="client/src/pages/Home.tsx:71:14" data-component-name="Card" class="rounded-lg border bg-card text-card-foreground shadow-sm p-3 sm:p-4"><div data-replit-metadata="client/src/pages/Home.tsx:72:16" data-component-name="div" class="flex justify-between items-center mb-1 sm:mb-2"><h3 data-replit-metadata="client/src/pages/Home.tsx:73:18" data-component-name="h3" class="text-sm font-medium">Total Budget</h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-dollar-sign h-4 w-4 text-muted-foreground" data-replit-metadata="client/src/pages/Home.tsx:74:18" data-component-name="CircleDollarSign"><circle cx="12" cy="12" r="10"></circle><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 18V6"></path></svg></div><div data-replit-metadata="client/src/pages/Home.tsx:79:16" data-component-name="div" class="text-xl sm:text-2xl font-bold">Rp&nbsp;7.300.000</div></div><div data-replit-metadata="client/src/pages/Home.tsx:85:14" data-component-name="Card" class="rounded-lg border bg-card text-card-foreground shadow-sm p-3 sm:p-4"><div data-replit-metadata="client/src/pages/Home.tsx:86:16" data-component-name="div" class="flex justify-between items-center mb-1 sm:mb-2"><h3 data-replit-metadata="client/src/pages/Home.tsx:87:18" data-component-name="h3" class="text-sm font-medium">Total Pengeluaran</h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-arrow-down h-4 w-4 text-muted-foreground" data-replit-metadata="client/src/pages/Home.tsx:88:18" data-component-name="ArrowDownCircle"><circle cx="12" cy="12" r="10"></circle><path d="M12 8v8"></path><path d="m8 12 4 4 4-4"></path></svg></div><div data-replit-metadata="client/src/pages/Home.tsx:93:16" data-component-name="div" class="text-xl sm:text-2xl font-bold text-destructive">Rp&nbsp;1.625.000</div></div><div data-replit-metadata="client/src/pages/Home.tsx:99:14" data-component-name="Card" class="rounded-lg border bg-card text-card-foreground shadow-sm p-3 sm:p-4"><div data-replit-metadata="client/src/pages/Home.tsx:100:16" data-component-name="div" class="flex justify-between items-center mb-1 sm:mb-2"><h3 data-replit-metadata="client/src/pages/Home.tsx:101:18" data-component-name="h3" class="text-sm font-medium">Sisa Budget</h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-arrow-up h-4 w-4 text-muted-foreground" data-replit-metadata="client/src/pages/Home.tsx:102:18" data-component-name="ArrowUpCircle"><circle cx="12" cy="12" r="10"></circle><path d="m16 12-4-4-4 4"></path><path d="M12 16V8"></path></svg></div><div data-replit-metadata="client/src/pages/Home.tsx:107:16" data-component-name="div" class="text-xl sm:text-2xl font-bold text-green-600">Rp&nbsp;5.675.000</div></div></div></div></div></section><section data-replit-metadata="client/src/pages/Home.tsx:118:6" data-component-name="section" class="mb-8 flex justify-center"><div data-replit-metadata="client/src/pages/Home.tsx:119:8" data-component-name="div" class="grid grid-cols-2 gap-4 w-full"><button data-replit-metadata="client/src/pages/Home.tsx:120:10" data-component-name="Button" class="gap-2 whitespace-nowrap rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0 bg-secondary text-secondary-foreground hover:bg-secondary/80 flex flex-col items-center justify-center h-20 p-2"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-dollar-sign h-6 w-6 mb-1" data-replit-metadata="client/src/pages/Home.tsx:125:12" data-component-name="CircleDollarSign"><circle cx="12" cy="12" r="10"></circle><path d="M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8"></path><path d="M12 18V6"></path></svg><span data-replit-metadata="client/src/pages/Home.tsx:126:12" data-component-name="span" class="text-xs text-center">Kelola Budget</span></button><button data-replit-metadata="client/src/pages/Home.tsx:128:10" data-component-name="Button" class="gap-2 whitespace-nowrap rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0 bg-secondary text-secondary-foreground hover:bg-secondary/80 flex flex-col items-center justify-center h-20 p-2"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-arrow-down h-6 w-6 mb-1" data-replit-metadata="client/src/pages/Home.tsx:133:12" data-component-name="ArrowDownCircle"><circle cx="12" cy="12" r="10"></circle><path d="M12 8v8"></path><path d="m8 12 4 4 4-4"></path></svg><span data-replit-metadata="client/src/pages/Home.tsx:134:12" data-component-name="span" class="text-xs text-center">Catat Pengeluaran</span></button></div></section><section data-replit-metadata="client/src/pages/Home.tsx:140:6" data-component-name="section" class="mb-8"><h2 data-replit-metadata="client/src/pages/Home.tsx:141:8" data-component-name="h2" class="text-xl sm:text-2xl font-semibold mb-4 text-center">Kenapa BudgetKu?</h2><div data-replit-metadata="client/src/pages/Home.tsx:142:8" data-component-name="div" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4"><div data-replit-metadata="client/src/pages/Home.tsx:143:10" data-component-name="div" class="bg-card p-4 rounded-lg shadow-sm"><div data-replit-metadata="client/src/pages/Home.tsx:144:12" data-component-name="div" class="w-10 h-10 flex items-center justify-center bg-primary/10 rounded-full mb-3"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-chart-pie h-5 w-5 text-primary" data-replit-metadata="client/src/pages/Home.tsx:145:14" data-component-name="PieChart"><path d="M21 12c.552 0 1.005-.449.95-.998a10 10 0 0 0-8.953-8.951c-.55-.055-.998.398-.998.95v8a1 1 0 0 0 1 1z"></path><path d="M21.21 15.89A10 10 0 1 1 8 2.83"></path></svg></div><h3 data-replit-metadata="client/src/pages/Home.tsx:147:12" data-component-name="h3" class="text-base font-medium mb-1">Visualisasi yang Jelas</h3><p data-replit-metadata="client/src/pages/Home.tsx:148:12" data-component-name="p" class="text-sm text-muted-foreground">Lihat pengeluaran dan budget Anda dalam tampilan visual yang mudah dipahami.</p></div><div data-replit-metadata="client/src/pages/Home.tsx:152:10" data-component-name="div" class="bg-card p-4 rounded-lg shadow-sm"><div data-replit-metadata="client/src/pages/Home.tsx:153:12" data-component-name="div" class="w-10 h-10 flex items-center justify-center bg-primary/10 rounded-full mb-3"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-wallet-cards h-5 w-5 text-primary" data-replit-metadata="client/src/pages/Home.tsx:154:14" data-component-name="WalletCards"><rect width="18" height="18" x="3" y="3" rx="2"></rect><path d="M3 9a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2"></path><path d="M3 11h3c.8 0 1.6.3 2.1.9l1.1.9c1.6 1.6 4.1 1.6 5.7 0l1.1-.9c.5-.5 1.3-.9 2.1-.9H21"></path></svg></div><h3 data-replit-metadata="client/src/pages/Home.tsx:156:12" data-component-name="h3" class="text-base font-medium mb-1">Kategorisasi Cerdas</h3><p data-replit-metadata="client/src/pages/Home.tsx:157:12" data-component-name="p" class="text-sm text-muted-foreground">Organisir pengeluaran berdasarkan kategori untuk melihat pola belanja Anda.</p></div><div data-replit-metadata="client/src/pages/Home.tsx:161:10" data-component-name="div" class="bg-card p-4 rounded-lg shadow-sm sm:col-span-2 md:col-span-1"><div data-replit-metadata="client/src/pages/Home.tsx:162:12" data-component-name="div" class="w-10 h-10 flex items-center justify-center bg-primary/10 rounded-full mb-3"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-circle-arrow-up h-5 w-5 text-primary" data-replit-metadata="client/src/pages/Home.tsx:163:14" data-component-name="ArrowUpCircle"><circle cx="12" cy="12" r="10"></circle><path d="m16 12-4-4-4 4"></path><path d="M12 16V8"></path></svg></div><h3 data-replit-metadata="client/src/pages/Home.tsx:165:12" data-component-name="h3" class="text-base font-medium mb-1">Limit Pengeluaran</h3><p data-replit-metadata="client/src/pages/Home.tsx:166:12" data-component-name="p" class="text-sm text-muted-foreground">Tetapkan batas pengeluaran dan dapatkan kendali penuh atas keuangan Anda.</p></div></div></section><section data-replit-metadata="client/src/pages/Home.tsx:174:6" data-component-name="section" class="mb-8"><div data-replit-metadata="client/src/pages/Home.tsx:175:8" data-component-name="div" class="grid grid-cols-1 sm:grid-cols-2 gap-4"><div data-replit-metadata="client/src/pages/Home.tsx:176:10" data-component-name="div" class="bg-card p-4 rounded-lg shadow-sm"><h3 data-replit-metadata="client/src/pages/Home.tsx:177:12" data-component-name="h3" class="text-base font-medium mb-3">Budget Aktif</h3><div data-replit-metadata="client/src/pages/Home.tsx:184:12" data-component-name="div"><p data-replit-metadata="client/src/pages/Home.tsx:185:16" data-component-name="p" class="text-2xl font-bold mb-1">3</p><p data-replit-metadata="client/src/pages/Home.tsx:186:16" data-component-name="p" class="text-sm text-muted-foreground mb-3">Budget yang sedang aktif</p><button data-replit-metadata="client/src/pages/Home.tsx:187:16" data-component-name="Button" class="inline-flex items-center justify-center gap-2 whitespace-nowrap text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0 border border-input bg-background hover:bg-accent hover:text-accent-foreground h-9 rounded-md px-3 w-full">Lihat Semua Budget</button></div></div><div data-replit-metadata="client/src/pages/Home.tsx:199:10" data-component-name="div" class="bg-card p-4 rounded-lg shadow-sm"><h3 data-replit-metadata="client/src/pages/Home.tsx:200:12" data-component-name="h3" class="text-base font-medium mb-3">Pengeluaran Tercatat</h3><div data-replit-metadata="client/src/pages/Home.tsx:207:12" data-component-name="div"><p data-replit-metadata="client/src/pages/Home.tsx:208:16" data-component-name="p" class="text-2xl font-bold mb-1">3</p><p data-replit-metadata="client/src/pages/Home.tsx:209:16" data-component-name="p" class="text-sm text-muted-foreground mb-3">Transaksi yang sudah tercatat</p><button data-replit-metadata="client/src/pages/Home.tsx:210:16" data-component-name="Button" class="inline-flex items-center justify-center gap-2 whitespace-nowrap text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0 border border-input bg-background hover:bg-accent hover:text-accent-foreground h-9 rounded-md px-3 w-full">Lihat Semua Transaksi</button></div></div></div></section><section data-replit-metadata="client/src/pages/Home.tsx:225:6" data-component-name="section" class="bg-primary text-primary-foreground p-4 sm:p-6 rounded-lg mb-6"><div data-replit-metadata="client/src/pages/Home.tsx:226:8" data-component-name="div" class="text-center"><h2 data-replit-metadata="client/src/pages/Home.tsx:227:10" data-component-name="h2" class="text-lg sm:text-xl font-semibold mb-2">Siap mengelola keuangan dengan lebih baik?</h2><p data-replit-metadata="client/src/pages/Home.tsx:228:10" data-component-name="p" class="text-sm mb-4 max-w-md mx-auto">Mulai catat pengeluaran dan atur budget Anda sekarang. Tanpa biaya, mudah digunakan.</p><button data-replit-metadata="client/src/pages/Home.tsx:231:10" data-component-name="Button" class="inline-flex items-center justify-center gap-2 whitespace-nowrap rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0 bg-secondary text-secondary-foreground hover:bg-secondary/80 h-10 px-4 py-2 w-full sm:w-auto">Mulai Sekarang</button></div></section></main></div><footer data-replit-metadata="client/src/components/layout/Footer.tsx:11:4" data-component-name="footer" class="py-6 bg-background border-t hidden md:block"><div data-replit-metadata="client/src/components/layout/Footer.tsx:12:6" data-component-name="div" class="container mx-auto px-4"><div data-replit-metadata="client/src/components/layout/Footer.tsx:13:8" data-component-name="div" class="text-center text-sm text-muted-foreground"><p data-replit-metadata="client/src/components/layout/Footer.tsx:14:10" data-component-name="p">© 2025 BudgetKu. Semua hak dilindungi.</p><p data-replit-metadata="client/src/components/layout/Footer.tsx:15:10" data-component-name="p" class="mt-2">Aplikasi manajemen keuangan yang mudah digunakan untuk mengontrol pengeluaran Anda.</p></div></div></footer></div><div role="region" aria-label="Notifications (F8)" tabindex="-1" style="pointer-events: none;"><ol tabindex="-1" data-replit-metadata="client/src/components/ui/toaster.tsx:30:6" data-component-name="ToastViewport" class="fixed top-0 z-[100] flex max-h-screen w-full flex-col-reverse p-4 sm:bottom-0 sm:right-0 sm:top-auto sm:flex-col md:max-w-[420px]"></ol></div></div>
    <script type="module" src="/src/main.tsx?v=ALPgHFaoO_p_330ZPt3w1"></script>
  

</body></html>
