<template>
    <div class="messagedefilant">
        <div data-text="Site internet - CMS - Web design - Site internet - CMS - Web design - Site internet - CMS - Web design - Site internet">
            <span>Site internet - CMS - Web design - Site internet - CMS - Web design - Site internet - CMS - Web design - Site internet</span>
        </div>
    </div>    
</template>

<style>
.messagedefilant {
    display: block;
    overflow: hidden;
    position: relative;
    width: 100%;
    max-width: 1920px;
    height: 78px;
}
 
.messagedefilant div {
    position: absolute;
    min-width: 100%;
    text-transform: uppercase;
}
 
.messagedefilant div span, 
.messagedefilant div:after {
  position: relative;
  display: inline-block;
  font-size: 2rem;
  white-space: nowrap;
  top:0;
}
 
.messagedefilant div span {
  animation: defilement 10s infinite linear;
  background: #323232;
  color: #f6bd60;
  padding: 15px;
}
 
.messagedefilant div:after {
  position: absolute;
  top:0; left:0;
  content:attr(data-text);
  animation: defilement2 10s infinite linear;
  background: #323232;
  color: #f6bd60;     
  padding: 15px;
}
 
@keyframes defilement {
  0% { margin-left: 0; }
  100% { margin-left: -100%; }
}
@keyframes defilement2 {
  0% { margin-left: 100%; }
  100% { margin-left: 0%; }
}
</style>