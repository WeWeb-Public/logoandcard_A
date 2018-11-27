<template>
    <div class="logoandcard_A">
        <!-- wwManager:start -->
        <wwSectionEditMenu v-bind:sectionCtrl="sectionCtrl"></wwSectionEditMenu>
        <!-- wwManager:end -->
        <wwObject class="background" v-bind:ww-object="section.data.background" ww-category="background"></wwObject>
        <div class="title">
            <wwObject v-bind:ww-object="section.data.title"></wwObject>
        </div>

        <div class="content-container">
            <div class="leftMargin"></div>
            <div class="logo-container small">
                <wwLayoutColumn tag="div" ww-default="ww-image" :ww-list="section.data.columns[4]" @ww-add="add(section.data.columns[4], $event)" @ww-remove="remove(section.data.columns[4], $event)">
                    <div class="logo-block" v-on:click="selectBlock(block)" v-for="(block, index) in section.data.columns[4]" :key="index">
                        <wwObject class="block-img logo" v-bind:ww-object="block.logo" v-bind:class="{ active: activeBlock && activeBlock.uniqueId == block.uniqueId }"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
            <div class="logo-container medium">
                <wwLayoutColumn tag="div" ww-default="ww-image" :ww-list="section.data.columns[2]" @ww-add="add(section.data.columns[2], $event)" @ww-remove="remove(section.data.columns[2], $event)">
                    <div class="logo-block" v-on:click="selectBlock(block)" v-for="(block, index) in section.data.columns[2]" :key="index">
                        <wwObject class="block-img logo" v-bind:ww-object="block.logo" v-bind:class="{ active: activeBlock && activeBlock.uniqueId == block.uniqueId }"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
            <div class="logo-container large">
                <wwLayoutColumn tag="div" ww-default="ww-image" :ww-list="section.data.columns[0]" @ww-add="add(section.data.columns[0], $event)" @ww-remove="remove(section.data.columns[0], $event)">
                    <div class="logo-block" v-on:click="selectBlock(block)" v-for="(block, index) in section.data.columns[0]" :key="index">
                        <wwObject class="block-img logo" v-bind:ww-object="block.logo" v-bind:class="{ active: activeBlock && activeBlock.uniqueId == block.uniqueId }"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
            <div class="container-block" v-if="activeBlock">
                <div class="card anim-ease-in-out opacity">
                    <wwObject class="background" v-bind:ww-object="activeBlock.background" ww-category="background"></wwObject>
                    <wwObject class="text" v-bind:ww-object="activeBlock.quote"></wwObject>
                    <div class="img-corner">
                        <wwObject class="block-img" v-bind:ww-object="activeBlock.secondLogo"></wwObject>
                    </div>
                </div>
                <div>
                    <wwObject v-bind:ww-object="section.data.margin"></wwObject>
                </div>
                <div>
                    <div class="al-container">
                        <div v-on:click="previous()" class="anim-ease-in-out opacity moveRight cursor-pointer">
                            <wwObject v-bind:ww-object="section.data.btnRight"></wwObject>
                        </div>
                        <div class="al-content">
                            <wwObject v-bind:ww-object="activeBlock.portrait" class="block-img al-portrait anim-ease-in-out opacity moveRight"></wwObject>
                            <div class="al-text anim-ease-in-out opacity moveRight">
                                <wwObject v-bind:ww-object="activeBlock.name" class="text"></wwObject>
                                <wwObject v-bind:ww-object="activeBlock.description" class="text"></wwObject>
                            </div>
                            <div class="al-btn anim-ease-in-out opacity moveLeft">
                                <wwObject v-bind:ww-object="activeBlock.btn"></wwObject>
                            </div>
                        </div>
                        <div v-on:click="next()" class="anim-ease-in-out opacity moveLeft cursor-pointer">
                            <wwObject v-bind:ww-object="section.data.btnLeft"></wwObject>
                        </div>
                    </div>
                    <div class="al-btn2 anim-ease-in-out opacity">
                        <wwObject v-bind:ww-object="activeBlock.btn"></wwObject>
                    </div>
                </div>
            </div>
            <div class="logo-container large">
                <wwLayoutColumn tag="div" ww-default="ww-image" :ww-list="section.data.columns[1]" @ww-add="add(section.data.columns[1], $event)" @ww-remove="remove(section.data.columns[1], $event)">
                    <div class="logo-block" v-on:click="selectBlock(block)" v-for="(block, index) in section.data.columns[1]" :key="index">
                        <wwObject class="block-img logo" v-bind:ww-object="block.logo" v-bind:class="{ active: activeBlock && activeBlock.uniqueId == block.uniqueId }"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
            <div class="logo-container medium">
                <wwLayoutColumn tag="div" ww-default="ww-image" :ww-list="section.data.columns[3]" @ww-add="add(section.data.columns[3], $event)" @ww-remove="remove(section.data.columns[3], $event)">
                    <div class="logo-block" v-on:click="selectBlock(block)" v-for="(block, index) in section.data.columns[3]" :key="index">
                        <wwObject class="block-img logo" v-bind:ww-object="block.logo" v-bind:class="{ active: activeBlock && activeBlock.uniqueId == block.uniqueId }"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
            <div class="logo-container small">
                <wwLayoutColumn tag="div" ww-default="ww-image" :ww-list="section.data.columns[5]" @ww-add="add(section.data.columns[5], $event)" @ww-remove="remove(section.data.columns[5], $event)">
                    <div class="logo-block" v-on:click="selectBlock(block)" v-for="(block, index) in section.data.columns[5]" :key="index">
                        <wwObject class="block-img logo" v-bind:ww-object="block.logo" v-bind:class="{ active: activeBlock && activeBlock.uniqueId == block.uniqueId }"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
        </div>
        <div class="full-width">
            <wwObject v-bind:ww-object="section.data.marginBottom"></wwObject>
        </div>
    </div>
</template>

<script>
export default {
    name: "logoandcard_A",
    props: {
        sectionCtrl: Object
    },
    data() {
        return {
            sectionId: null,
            inteval: null,
            activeBlock: null,
            idx: 0
        };
    },
    computed: {
        section() {
            return this.sectionCtrl.get();
        },
        activeColumn() {
            for (const columnIndex in this.section.data.columns) {
                for (const block of this.section.data.columns[columnIndex]) {
                    if (block && block.uniqueId == this.activeBlock.uniqueId) {
                        return columnIndex;
                    }
                }
            }
            return 0;
        },
        activeRow() {
            for (const columnIndex in this.section.data.columns) {
                for (const blockIndex of this.section.data.columns[columnIndex]) {
                    if (this.section.data.columns[columnIndex][blockIndex] && this.section.data.columns[columnIndex][blockIndex].uniqueId == this.activeBlock.uniqueId) {
                        return blockIndex;
                    }
                }
            }
            return 0;
        }
    },
    methods: {
        initData() {

            //Init objects
            let needUpdate = this.migrateData();
            if (!this.section.data.background) {
                this.section.data.background = wwLib.wwObject.getDefault({ type: 'ww-color', data: { color: 'white' } });
                needUpdate = true;
            }
            if (!this.section.data.title) {
                this.section.data.title = wwLib.wwObject.getDefault({ type: 'ww-text' });
                needUpdate = true;
            }
            if (!this.section.data.btnLeft) {
                this.section.data.btnLeft = wwLib.wwObject.getDefault({ type: 'ww-icon' });
                needUpdate = true;
            }
            if (!this.section.data.btnRight) {
                this.section.data.btnRight = wwLib.wwObject.getDefault({ type: 'ww-icon' });
                needUpdate = true;
            }


            if (needUpdate) {
                this.sectionCtrl.update(this.section);
            }

        },
        migrateData() {

            if (!this.section.data.block) {
                return false;
            }

            this.section.data.columns = [
                [], [], [], [], [], []
            ];

            for (const index in this.section.data.block) {
                let block = this.section.data.block[index];
                if (block) {
                    let colIndex = index % 6;
                    this.section.data.block[index].uniqueId = wwLib.wwUtils.getUniqueId();
                    this.section.data.columns[colIndex].push(this.section.data.block[index]);
                }
            }

            if (this.section.data.columns[0] && this.section.data.columns[0][0]) {
                this.activeBlock = this.section.data.columns[0][0];
            }

            console.log(this.activeBlock)

            delete this.section.data.block;
            return true;
        },
        init: function () {
            //console.log(this.section.data.block)
            this.sectionId = this.section.id

            this.setTimer()
        },
        timeout(ms) {
            return new Promise(resolve => setTimeout(resolve, ms));
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
            await this.timeout(500)
        },
        setTimer: function () {
            const self = this
            this.interval = setInterval(function () {
                // if (!$scope.editingSection)
                self.changeData(self.getNextBlock(self.activeColumn, self.activeRow))
            }, 8000);
        },
        changeData: async function (block) {
            await this.removeAnim()
            this.activeBlock = block;
            await this.activeAnim()
        },
        getNextBlock(c, r) {
            const maxColumns = 5;
            let maxRows = 0;
            for (const columnIndex in this.section.data.columns) {
                maxRows = Math.max(maxRows, this.section.data.columns[columnIndex].length);
            }
            if (maxRows == 0) {
                return null;
            }
            c++;
            if (c > maxColumns) {
                c = 0;
                r++;
            }
            if (r > maxRows - 1) {
                r = 0;
            }
            if (!this.section.data.columns[c][r]) {
                return this.getNextBlock(c, r);
            }
            return this.section.data.columns[c][r];
        },
        getPreviousBlock(c, r) {
            const maxColumns = 5;
            let maxRows = 0;
            for (const columnIndex in this.section.data.columns) {
                maxRows = Math.max(maxRows, this.section.data.columns[columnIndex].length);
            }
            if (maxRows == 0) {
                return null;
            }
            c--;
            if (c < 0) {
                c = maxColumns;
                r--;
            }
            if (r < 0) {
                r = maxRows - 1;
            }
            if (!this.section.data.columns[c][r]) {
                return this.getPreviousBlock(c, r);
            }
            return this.section.data.columns[c][r];
        },
        next: async function () {
            console.log(this.activeColumn, this.activeRow)
            await this.changeData(this.getNextBlock(this.activeColumn, this.activeRow))
            clearInterval(this.interval)
            this.setTimer()
        },
        previous: async function () {
            await this.changeData(this.getPreviousBlock(this.activeColumn, this.activeRow))
            clearInterval(interval)
            this.setTimer()
        },
        selectBlock: async function (block) {
            clearInterval(this.interval)
            await this.changeData(block)
            this.setTimer()
        },
        getNewBlock() {
            return {
                uniqueId: wwLib.wwUtils.getUniqueId(),
                logo: wwLib.wwObject.getDefault({ type: 'ww-image', ratio: 100, data: { classes: ["ww-class-img-format-round-small", "ww-class-img-shadow-box-medium"] } }),
                background: wwLib.wwObject.getDefault({ type: 'ww-color' }),
                quote: wwLib.wwObject.getDefault({ type: 'ww-text', data: { color: 'white' } }),
                secondLogo: wwLib.wwObject.getDefault({ type: 'ww-image' }),
                portrait: wwLib.wwObject.getDefault({ type: 'ww-image' }),
                name: wwLib.wwObject.getDefault({ type: 'ww-text' }),
                description: wwLib.wwObject.getDefault({ type: 'ww-text' }),
                btn: wwLib.wwObject.getDefault({ type: 'ww-button' }),
            }
        },
        add(column, options) {

            column.splice(options.index, 0, this.getNewBlock());
            this.sectionCtrl.update(this.section);
        },
        remove(column, options) {
            column.splice(options.index, 1);
            this.sectionCtrl.update(this.section);
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
    created() {
        this.initData();
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
    padding-top: 15px;
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
