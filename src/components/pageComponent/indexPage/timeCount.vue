<!--倒计时组件-->
<template>
    <div class="timecount">
        <span class="timecount-span">
        {{hour}}
        </span>:
        <span class="timecount-span">
        {{minute}}
        </span>:
        <span class="timecount-span">
        {{second}}
        </span>
    </div>
</template>

<script>
/**
 * 处理显示的时间
 */
function getTimeDetail(time){
    time = parseInt(time / 1000); // 总共多少秒
    let second = parseInt(time % 60); // 秒
    if (second < 10) {
        second = '0' + second;
    }

    time = parseInt(time / 60); // 总共多少分
    let minute = parseInt(time % 60); // 分
    if (minute < 10) {
        minute = '0' + minute;
    }

    time = parseInt(time / 60); // 总共多少小时
    if ( time < 10) {
        time = '0' + time;
    }

    return {
        hour: time,
        minute,
        second
    }
}

export default {
    name: 'timeCount',
    props: {
        endTime: {
            type: String
        }
    },
    data () {
        return {
            hour:'00',
            minute:'00',
            second:'00'
        }
    },
    created() {
        const lestTime = new Date(this.endTime).getTime() - new Date().getTime();
        countTimeDown(lestTime, this);

        function countTimeDown(lestTime, self){
            const timeDetail = getTimeDetail(lestTime);
            self.hour = timeDetail.hour;
            self.minute = timeDetail.minute;
            self.second = timeDetail.second;

            if ( lestTime > 0 ) {
                setTimeout(function(){
                    lestTime = lestTime - 1000;
                    countTimeDown(lestTime, self);
                }, 1000);
            }
        }
    }
}
</script>

<style>
    .timecount-span {
        display: inline-block;
        background-color: #4C4C4C;
        width: .4rem;
        height: .3rem;
        border-radius: .06rem;
        text-align: center;
        line-height: .3rem;
        font-size: .24rem;
        color: #fff;
    }
</style>
