<template>
    <div>
        <div class="etabs-tabgroup">
            <div class="etabs-tabs"></div>
            <div class="etabs-buttons"></div>
        </div>
        <div class="etabs-views">
        </div>
    </div>
</template>
<script>
    import TabGroup from 'electron-tabs'
    export default {
        name: 'TabGroup',
        mounted() {
            let tabGroup = new TabGroup({
                ready : function(){
                    console.log("ready");
                    console.log(document.getElementsByTagName("webview"));
                    let webview = document.getElementsByTagName("webview");
                    for(const p of webview){
                        console.log(p);
                       // webview.setAttribute("allowpopups")
                    }
                }
            });
            tabGroup.on("tab-added", (tab) => {
                console.log(tab);
                //tab.webview.setAttribute("allowpopups","");
            })
            tabGroup.addTab({
                title: "Portal",
                src: "https://portal.daou.co.kr",
                visible: true,
                webviewAttributes : {
                    "allowpopups" : true
                }
            });
            tabGroup.addTab({
                title: "Jira",
                src: "https://issue.daou.co.kr",
                visible: true,
                active : true,
                webviewAttributes : {
                    "allowpopups" : true
                }
            });
            tabGroup.addTab({
                title: "Stash",
                src: "https://stash.daou.co.kr",
                visible: true,
                webviewAttributes : {
                    "allowpopups" : true
                }
            });
        }
    };
</script>