<template lang="pug">
    //- 主游戏区
    div.playpanel
        div.table-panel(v-el:panel,v-bind:style="{width:imgSize.width*zoomRate.x+'px',height:imgSize.height*zoomRate.y+'px'}")
            div.num.single(v-bind:style="single",@touchend="dobet('single')")
                img.chip(v-for="item in bets|filterBy 'single' in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum('single')",v-html="betsum('single')")
            div.num.double(v-bind:style="double",@touchend="dobet('double')")
                img.chip(v-for="item in bets|filterBy 'double' in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum('double')",v-html="betsum('double')")
            div.num.zero(v-bind:style="zero",@touchend="dobet(0)")
                img.chip(v-for="item in bets|filterBy 0 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(0)",v-html="betsum(0)")
            div.num.one(v-bind:style="one",@touchend="dobet(1)")
                img.chip(v-for="item in bets|filterBy 1 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(1)",v-html="betsum(1)")
            div.num.two(v-bind:style="two",@touchend="dobet(2)")
                img.chip(v-for="item in bets|filterBy 2 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(2)",v-html="betsum(2)")
            div.num.three(v-bind:style="three",@touchend="dobet(3)")
                img.chip(v-for="item in bets|filterBy 3 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(3)",v-html="betsum(3)")
            div.num.four(v-bind:style="four",@touchend="dobet(4)")
                img.chip(v-for="item in bets|filterBy 4 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(4)",v-html="betsum(4)")
            div.num.five(v-bind:style="five",@touchend="dobet(5)")
                img.chip(v-for="item in bets|filterBy 5 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(5)",v-html="betsum(5)")
            div.num.six(v-bind:style="six",@touchend="dobet(6)")
                img.chip(v-for="item in bets|filterBy 6 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(6)",v-html="betsum(6)")
            div.num.seven(v-bind:style="seven",@touchend="dobet(7)")
                img.chip(v-for="item in bets|filterBy 7 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(7)",v-html="betsum(7)")
            div.num.eight(v-bind:style="eight",@touchend="dobet(8)")
                img.chip(v-for="item in bets|filterBy 8 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(8)",v-html="betsum(8)")
            div.num.nine(v-bind:style="nine",@touchend="dobet(9)")
                img.chip(v-for="item in bets|filterBy 9 in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum(9)",v-html="betsum(9)")
            div.num.big(v-bind:style="big",@touchend="dobet('big')")
                img.chip(v-for="item in bets|filterBy 'big' in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum('big')",v-html="betsum('big')")
            div.num.small(v-bind:style="small",@touchend="dobet('small')")
                img.chip(v-for="item in bets|filterBy 'small' in 'betnum'",v-bind:src="item.betimg",v-bind:style="{margin: (Math.random() * 50) + '% 0 0 ' + (Math.random() * 50) + '%'}")
                p.bet-money-item(v-show="betsum('small')",v-html="betsum('small')")
        img(v-bind:src="tablePanelImg",style="margin:15% 0 0 5%;",v-bind:style="{width:imgSize.width*0.9*zoomRate.x+'px',height:imgSize.height*0.43*zoomRate.y+'px'}")
        img(v-bind:src="singleBigImg",style="margin:0% 0 0 5%;",v-bind:style="{width:imgSize.width*0.9*zoomRate.x+'px',height:imgSize.height*0.25*zoomRate.y+'px'}")
</template>
<script>
    export default {
        props: ['zoomRate', 'userinfo', 'lastbets', 'bets', 'userBet', 'countDown', 'countNum', 'lockmoney', 'lotterynum', 'chipImg','limitDown'],
        data() {
            return {
                showBetNum: '', //中奖后在方块中显示此数字
                tablePanelImg: require('../assets/修改切图/数字.png'),
                singleBigImg: require('../assets/修改切图/大小单双.png'),
                imgSize: {
                    width: 640,
                    height: 528
                }
            }
        },
        computed: {
            // TODO 重新设定中奖规则
            bonusNum() {
                var nums = this.lotterynum.lotterynums.split(',')
                var sum = parseInt(nums[0]) + parseInt(nums[nums.length - 1])
                var showsum = isNaN(sum) ? '?' : (Math.floor(sum / 10) ? Math.floor(sum / 10) : '') + '(' + sum % 10 + ')'
                var firstnum = isNaN(parseInt(nums[0])) ? '?' : parseInt(nums[0])
                var secnum = isNaN(parseInt(nums[nums.length - 1])) ? '?' : parseInt(nums[nums.length - 1])
                return firstnum + '+' + secnum + '=' + showsum
            },
            // 是否中奖 中奖的话显示为方块绿色
            isBouns() {
                var _this = this
                var nums = this.lotterynum.lotterynums.split(',')
                var sum = parseInt(nums[0]) + parseInt(nums[nums.length - 1])
                var checkBouns = (betnum, bonudnum) => { //判断是否中奖
                    if (betnum === bonudnum % 10) return true
                    if (betnum === 'single' && bonudnum % 2 === 1) return true
                    if (betnum === 'double' && bonudnum % 2 === 0) return true
                    if (betnum === 'big' && bonudnum >= 5) return true
                    if (betnum === 'small' && bonudnum < 5) return true

                    return false
                }
                this.lastbets ? this.lastbets.forEach((key, value) => {
                    if (this.userBet.idnum === value.idnum + 1 && checkBouns(value.betnum, sum)) { //只显示上次开奖结果
                        _this.showBetNum = value.betnum
                    }
                }) : ''
                return this.showBetNum || this.showBetNum === 0 ? this.showBetNum : ''
            },
            single() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 330 * this.zoomRate.y + 'px 0 0 ' + 340 * this.zoomRate.x + 'px'
                }
            },
            double() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 330 * this.zoomRate.y + 'px 0 0 ' + 490 * this.zoomRate.x + 'px'
                }
            },
            zero() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 90 * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 0) * this.zoomRate.x + 'px'
                }
            },
            one() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 90 * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 1) * this.zoomRate.x + 'px'
                }
            },
            two() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 90 * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 2) * this.zoomRate.x + 'px'
                }
            },
            three() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 90 * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 3) * this.zoomRate.x + 'px'
                }
            },
            four() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 90 * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 4) * this.zoomRate.x + 'px'
                }
            },
            five() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: (90 + 110) * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 0) * this.zoomRate.x + 'px'
                }
            },
            six() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: (90 + 110) * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 1) * this.zoomRate.x + 'px'
                }
            },
            seven() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: (90 + 110) * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 2) * this.zoomRate.x + 'px'
                }
            },
            eight() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: (90 + 110) * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 3) * this.zoomRate.x + 'px'
                }
            },
            nine() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: (90 + 110) * this.zoomRate.y + 'px 0 0 ' + (35 + 115 * 4) * this.zoomRate.x + 'px'
                }
            },
            big() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 330 * this.zoomRate.y + 'px 0 0 ' + 40 * this.zoomRate.x + 'px'
                }
            },
            small() {
                return {
                    width: 110 * this.zoomRate.x + 'px',
                    height: 110 * this.zoomRate.y + 'px',
                    margin: 330 * this.zoomRate.y + 'px 0 0 ' + 190 * this.zoomRate.x + 'px'
                }
            },
            formula() {
                return {
                    width: 210 * this.zoomRate.x + 'px',
                    textAlign: 'center',
                    // height: 110 * this.zoomRate.y + 'px',
                    fontSize: 42 * this.zoomRate.x + 'px',
                    margin: 37 * this.zoomRate.y + 'px 0 0 ' + 220 * this.zoomRate.x + 'px'
                }
            },
            // TODO 遍历上期下注记录，计算筛选是否有中奖号码
            bonudnum() {
                return {
                    width: 68 * this.zoomRate.x + 'px',
                    textAlign: 'center',
                    fontSize: 40 * this.zoomRate.x + 'px',
                    height: 68 * this.zoomRate.y + 'px',
                    margin: 90 * this.zoomRate.y + 'px 0 0 ' + 290 * this.zoomRate.x + 'px',
                    backgroundImage: this.isBouns ? 'url(' + require('../assets/切图/主界面/显示-绿.png') + ')' : 'url(' + require('../assets/切图/主界面/显示-红.png') + ')'
                }
            }
        },
        methods: {
            betsum(index) { //单个下注总金额 ，比如下了多少金币在数字0上
                let result = 0
                this.bets.forEach(value => {
                    if (value.betnum == index) {
                        result += value.betmoney
                    }
                })
                return result
            },
            bet(event) {
                console.log('Height' + event.target.offsetHeight)
                console.log('Width' + event.target.offsetWidth)
                console.log(event)
            },
            // 用户下注
            dobet(num) {
                if (this.userinfo.money - this.userBet.betmoney - this.lockmoney < 0) return //余额小于0是禁止下注
                if (this.countDown < this.limitDown) return // 倒计时小于60秒时禁止下注
                if (Object.prototype.toString.call(num) === '[object Number]') {
                    this.userBet.type = 'NUMBER'
                    this.userBet.betnum = num
                } else if (Object.prototype.toString.call(num) === '[object String]') {
                    switch (num) {
                        case 'single':
                            this.userBet.type = 'SINGLE_OR_DOUBLE'
                            this.userBet.betnum = num
                            break
                        case 'double':
                            this.userBet.type = 'SINGLE_OR_DOUBLE'
                            this.userBet.betnum = num
                            break
                        case 'big':
                            this.userBet.type = 'BIG_OR_SMALL'
                            this.userBet.betnum = num
                            break
                        case 'small':
                            this.userBet.type = 'BIG_OR_SMALL'
                            this.userBet.betnum = num
                            break
                        default:
                            break
                    }
                }
                this.userBet.betimg = this.chipImg
                this.bets.push(Object.assign({}, this.userBet))
            }
        },
        events: {
            cancelBet(event) {
                this.bets = []
            }
        }
    }
</script>
<style>
    p {
        -moz-user-select: none;
        -webkit-user-select: none;
    }
    
    .playpanel {
        background: url('../assets/修改切图/主操作背景.png');
        background-size: cover;
        background-repeat: no-repeat;
        height: 50%;
        background-position: 50% 50%;
    }
    
    img.chip {
        width: 30%;
        height: 30%;
        position: absolute;
    }
    
    div.table-panel {
        width: 100%;
        height: 50%;
        position: absolute;
        /*display: none;*/
        /*background: rgba(255, 0, 0, .3);*/
    }
    
    div.single {
        /*background: rgba(0, 255, 255, .6);*/
        border-radius: 1em;
    }
    
    div.double {
        /*background: rgba(0, 255, 255, .6);*/
        margin: 3% 0% 0% 86%;
        border-radius: 1em;
    }
    
    div.big {
        border-radius: 1em;
    }
    
    div.small {
        border-radius: 1em;
    }
    
    div.num {
        position: absolute;
        /*background: rgba(0, 255, 255, .6);*/
    }
    
    p.bet-money-item {
        margin: 90% 0 0;
        float: left;
        background: rgba(0, 0, 0, .3);
        padding: 5px;
        border-radius: 10px;
        font-size: 12px;
        position: relative;
        color: rgb(250, 250, 250);
    }
    /*中奖*/
    
    div.bonudnum.active {
        /*background: url(../assets/切图/主界面/显示-绿.png) 50% 50%;*/
    }
    
    div.bonudnum {
        /*background: url(../assets/切图/主界面/显示-红.png) 50% 50%;*/
        background-size: contain;
        background-repeat: no-repeat;
        background-position: 50% 50%;
    }
</style>