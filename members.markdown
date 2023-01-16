---
layout: articles
titles:
  en      : &EN       Hall Of Fame
  en-GB   : *EN
  en-US   : *EN
  en-CA   : *EN
  en-AU   : *EN
  zh-Hans : &ZH_HANS  关于
  zh      : *ZH_HANS
  zh-CN   : *ZH_HANS
  zh-SG   : *ZH_HANS
  zh-Hant : &ZH_HANT  關於
  zh-TW   : *ZH_HANT
  zh-HK   : *ZH_HANT
  ko      : &KO       소개
  ko-KR   : *KO
key: page-members
---

<body>
  <div id="sticky-banner">WORK IN PROGRESS</div>
  <!-- rest of your webpage content -->
</body>
<style>
  #sticky-banner {
  background-color: red; /* or any other color you want */
  color: white;
  text-align: center;
  padding: 10px;
  position: -webkit-sticky; /* for Safari */
  position: sticky;
  top: 0; /* position at the top of the page */
  z-index: 1; /* make sure it appears on top of other elements */
}
</style>
<div class="grid-container">
   <div class="grid grid--p-3">
   {% for member in site.members %}
      <div class="cell cell--4">
         <div class="card">
            <div class="card__image">
                {% if member.custom_image%}
                    <img class="image" src="{{member.custom_image}}"/>
                {% else %}
                    <img src="https://api.dicebear.com/5.x/adventurer-neutral/svg?seed={{ member.name }}"/>
                {% endif %}
            </div>
            <div class="card__content">
               <div class="card__header">
                  <h4><a href="{{member.steam }}">{{ member.name }}</a></h4>
                  <h5>{{member.position}}</h5>
               </div>
               <p>{{ member.content | markdownify }}</p>
            </div>
         </div>
      </div>
    {% endfor %}
   </div>
</div>


