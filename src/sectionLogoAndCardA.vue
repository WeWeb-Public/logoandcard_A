<template>
    <div class="logoandcard_A">

        <!-- wwManager:start -->
        <wwSectionEditMenu v-bind:section="section"></wwSectionEditMenu>
        <!-- wwManager:end -->

        <wwObject class="background" v-bind:ww-object="section.data.background" ww-category="background"></wwObject>
        <div class="title">
            <wwObject v-bind:ww-object="section.data.title"></wwObject>
        </div>

        <div class="content-container">
            <div class="leftMargin"></div>
            <div class="logo-container small">
                <div>
                    <div v-if="section.data.block[4]" class="logo-block" v-on:click="selectIdx(4)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[4].logo" v-bind:class="{ active: idx === 4 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[10]" class="logo-block" v-on:click="selectIdx(10)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[10].logo" v-bind:class="{ active: idx === 10 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[14]" class="logo-block" v-on:click="selectIdx(14)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[14].logo" v-bind:class="{ active: idx === 14 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[16]" class="logo-block" v-on:click="selectIdx(16)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[16].logo" v-bind:class="{ active: idx === 16 }"></wwObject>
                    </div>
                </div>
            </div>
            <div class="logo-container medium">
                <div>
                    <div v-if="section.data.block[2]" class="logo-block" v-on:click="selectIdx(2)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[2].logo" v-bind:class="{ active: idx === 2 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[8]" class="logo-block" v-on:click="selectIdx(8)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[8].logo" v-bind:class="{ active: idx === 8 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[12]" class="logo-block" v-on:click="selectIdx(12)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[12].logo" v-bind:class="{ active: idx === 12 }"></wwObject>
                    </div>
                </div>
            </div>
            <div class="logo-container large">
                <div>
                    <div v-if="section.data.block[0]" class="logo-block" v-on:click="selectIdx(0)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[0].logo" v-bind:class="{ active: idx === 0 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[6]" class="logo-block" v-on:click="selectIdx(6)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[6].logo" v-bind:class="{ active: idx === 6 }"></wwObject>
                    </div>
                </div>
            </div>
            <div class="container-block">
                <div class="card anim-ease-in-out opacity">
                    <wwObject class="background" v-bind:ww-object="section.data.block[idx].background" ww-category="background"></wwObject>
                    <wwObject class="text" v-bind:ww-object="section.data.block[idx].quote"></wwObject>
                    <div class="img-corner">
                        <wwObject class="block-img" v-bind:ww-object="section.data.block[idx].secondLogo"></wwObject>
                    </div>
                </div>
                <div>
                    <wwObject v-bind:ww-object="section.data.margin"></wwObject>
                </div>
                <div>
                    <div class="al-container">
                        <div v-on:click="decrIdx()" class="anim-ease-in-out opacity moveRight cursor-pointer">
                            <wwObject v-bind:ww-object="section.data.btnRight"></wwObject>
                        </div>
                        <div class="al-content">
                            <wwObject v-bind:ww-object="section.data.block[idx].portrait" class="block-img al-portrait anim-ease-in-out opacity moveRight"></wwObject>
                            <div class="al-text anim-ease-in-out opacity moveRight">
                                <wwObject v-bind:ww-object="section.data.block[idx].name" class="text"></wwObject>
                                <wwObject v-bind:ww-object="section.data.block[idx].description" class="text"></wwObject>
                            </div>
                            <div class="al-btn anim-ease-in-out opacity moveLeft">
                                <wwObject v-bind:ww-object="section.data.block[idx].btn"></wwObject>
                            </div>
                        </div>
                        <div v-on:click="incrIdx()" class="anim-ease-in-out opacity moveLeft cursor-pointer">
                            <wwObject v-bind:ww-object="section.data.btnLeft"></wwObject>
                        </div>
                    </div>
                    <div class="al-btn2 anim-ease-in-out opacity">
                        <wwObject v-bind:ww-object="section.data.block[idx].btn"></wwObject>
                    </div>
                </div>
            </div>
            <div class="logo-container large">
                <div>
                    <div v-if="section.data.block[1]" class="logo-block" v-on:click="selectIdx(1)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[1].logo" v-bind:class="{ active: idx === 1 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[7]" class="logo-block" v-on:click="selectIdx(7)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[7].logo" v-bind:class="{ active: idx === 7 }"></wwObject>
                    </div>
                </div>
            </div>
            <div class="logo-container medium">
                <div>
                    <div v-if="section.data.block[3]" class="logo-block" v-on:click="selectIdx(3)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[3].logo" v-bind:class="{ active: idx === 3 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[9]" class="logo-block" v-on:click="selectIdx(9)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[9].logo" v-bind:class="{ active: idx === 9 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[13]" class="logo-block" v-on:click="selectIdx(13)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[13].logo" v-bind:class="{ active: idx === 13 }"></wwObject>
                    </div>
                </div>
            </div>
            <div class="logo-container small">
                <div>
                    <div v-if="section.data.block[5]" class="logo-block" v-on:click="selectIdx(5)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[5].logo" v-bind:class="{ active: idx === 5 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[11]" class="logo-block" v-on:click="selectIdx(11)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[11].logo" v-bind:class="{ active: idx === 11 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[15]" class="logo-block" v-on:click="selectIdx(15)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[15].logo" v-bind:class="{ active: idx === 15 }"></wwObject>
                    </div>
                    <div v-if="section.data.block[17]" class="logo-block" v-on:click="selectIdx(17)">
                        <wwObject class="block-img logo" v-bind:ww-object="section.data.block[17].logo" v-bind:class="{ active: idx === 17 }"></wwObject>
                    </div>
                </div>
            </div>
        </div>
        <div class="full-width">
            <wwObject v-bind:ww-object="section.data.marginBottom"></wwObject>
        </div>
    </div>
</template>

<script>
function timeout(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
}
export default {
    name: "logoandcard_A",
    props: {
        sectionCtrl: Object
    },
    data() {
        return {
            section: this.sectionCtrl.get(),
            sectionId: null,
            inteval: null,
            idx: 0
        };
    },
    computed: {
    },
    methods: {
        init: function () {
            //console.log(this.section.data.block)
            this.sectionId = this.section.id
            this.section.data.block = this.section.data.block || []

            this.setTimer()
        },
        activeAnim: async function () {
            let sectionElement = this.$el
            const opacity = sectionElement.getElementsByClassName('opacity')
            const moveLeft = sectionElement.getElementsByClassName('moveLeft')
            const moveRight = sectionElement.getElementsByClassName('moveRight')

            for (let elem of opacity) {
                elem.style.opacity = 1
            }
            for (let elem of moveLeft) {
                elem.style.left = '0'
            }
            for (let elem of moveRight) {
                elem.style.left = '0'
            }
        },
        removeAnim: async function () {
            let sectionElement = this.$el
            const opacity = sectionElement.getElementsByClassName('opacity')
            const moveLeft = sectionElement.getElementsByClassName('moveLeft')
            const moveRight = sectionElement.getElementsByClassName('moveRight')

            for (let elem of opacity) {
                elem.style.opacity = 0
            }
            for (let elem of moveLeft) {
                elem.style.left = '-5px'
            }
            for (let elem of moveRight) {
                elem.style.left = '5px'
            }
            await timeout(500)
        },
        setTimer: function () {
            const self = this
            this.interval = setInterval(function () {
                // if (!$scope.editingSection)
                self.changeData((self.idx + 1) % self.section.data.block.length)
            }, 8000);
        },
        changeData: async function (idx) {
            await this.removeAnim()
            this.idx = idx
            await this.activeAnim()
        },
        incrIdx: async function () {
            await this.changeData((this.idx + 1) % this.section.data.block.length)
            clearInterval(this.interval)
            this.setTimer()
        },
        decrIdx: async function () {
            var idx = this.idx - 1
            if (idx < 0) idx = this.section.data.block.length - 1
            await this.changeData(idx)
            clearInterval(interval)
            this.setTimer()
        },
        selectIdx: async function (idx) {
            clearInterval(this.interval)
            await this.changeData(idx)
            this.setTimer()
        },
        addBlock: async function () {
            if (this.section.data.block.length > 17) {
                return
            }
            if (this.section.data.block.length > 0)
                this.section.data.block.push(JSON.parse(JSON.stringify(this.section.data.block[this.section.data.block.length - 1])))
            else
                this.section.data.block.push({})
            await this.changeData(this.section.data.block.length - 1)
        },
        removeBlock: function (idx) {
            this.section.data.block.splice(idx, 1)
            this.decrIdx()
        }
    },
    mounted: function () {
        this.idx = 0
        this.$nextTick(() => {
            this.init()
        })
    }
};
</script>

<style scoped>
.logoandcard_A {
  position: relative;
}

.logoandcard_A .background {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
}

.logoandcard_A .content-container {
  display: flex;
  width: 100%;
  overflow-x: hidden;
}

.logoandcard_A .f-container {
  display: flex;
}

.logoandcard_A .f-container .full-width {
  flex-basis: 100%;
}

.logoandcard_A .left-margin {
  flex-basis: 0.08333333%;
}

.logoandcard_A .contents {
  position: relative;
  width: 100%;
}

.logoandcard_A .top-padding-edit {
  height: 50px;
  width: 100%;
}

.logoandcard_A .ww-add-block-container {
  position: relative;
  text-align: center;
  padding: 15px;
}

.logoandcard_A .ww-add-block {
  position: relative;
  height: 70px;
  width: 70px;
  display: inline-block;
}

.logoandcard_A .row-container {
  width: 100%;
  position: relative;
}

.logoandcard_A .row-container.editing {
  padding-left: 100px;
}

.logoandcard_A .row-container > .edit-button-top-left {
  top: 2px;
  left: 2px;
}

.logoandcard_A .img-corner {
  position: absolute;
  right: 10px;
  bottom: 5px;
  width: 20%;
}

.logoandcard_A .logo-container {
  display: block;
  position: relative;
  float: left;
  box-sizing: border-box;
  min-height: 1px;
  padding-right: 9px;
  padding-left: 9px;
}

.logoandcard_A .cursor-pointer {
  cursor: pointer;
}

.logoandcard_A .small.logo-container {
  width: 8%;
}

.logoandcard_A .medium.logo-container {
  width: 8.5%;
}

.logoandcard_A .large.logo-container {
  width: 9%;
}

.logoandcard_A .logo-container .logo {
  transition: 1s;
  cursor: pointer;
  opacity: 0.5;
  margin-bottom: 10px;
}

.logoandcard_A .logo-container .logo.active,
.logoandcard_A .logo:hover {
  transform: translateY(-5px);
  transition: 1s;
  opacity: 1;
}

.logoandcard_A .container-block {
  position: relative;
  display: block;
  float: left;
  min-height: 1px;
  padding-right: 15px;
  padding-left: 15px;
  width: 47%;
}

.logoandcard_A .leftMargin {
  width: 1%;
  padding: unset;
  float: left;
}

.logoandcard_A .logo-block {
  position: relative;
}

.logoandcard_A .card {
  position: relative;
  height: 350px;
  display: inline-block;
  margin-bottom: 20px;
}

.logoandcard_A .al-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logoandcard_A .al-content {
  width: 85%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.logoandcard_A .al-portrait {
  float: left;
  width: 15%;
  height: 15%;
}

.logoandcard_A .al-text {
  width: 60%;
  position: relative;
}

.logoandcard_A .al-btn {
  position: relative;
}

.logoandcard_A .al-btn2 {
  display: none;
}

@media (max-width: 1200px) {
  .logoandcard_A .img-corner {
    width: 30%;
  }
}

@media (max-width: 992px) {
  .logoandcard_A .logo-container {
    display: none;
  }

  .logoandcard_A .container-block {
    width: 96%;
  }

  .logoandcard_A .img-corner {
    width: 15%;
  }
}

@media (max-width: 769px) {
  .logoandcard_A .img-corner {
    width: 20%;
  }
  .logoandcard_A .al-text {
    width: 80%;
  }
  .logoandcard_A .al-btn {
    display: none;
  }
  .logoandcard_A .al-btn2 {
    width: 100%;
    text-align: center;
    margin: auto;
    display: block;
  }
}

@media (max-width: 555px) {
  .logoandcard_A .img-corner {
    width: 30%;
  }
}

.logoandcard_A .anim-ease-in-out {
  -webkit-transition: all 0.5s ease-in-out;
  -moz-transition: all 0.5s ease-in-out;
  -ms-transition: all 0.5s ease-in-out;
  -o-transition: all 0.5s ease-in-out;
  transition: all 0.5s ease-in-out;
  position: relative;
}
</style>
