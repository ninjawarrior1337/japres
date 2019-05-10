<template>
    <section>
        <section>
            <h3>Basic Grammar</h3>
            <h4>Let's look at a basic sentance</h4>
        </section>
        <section>
            <div>
                <h2>
                    <span class="partofspeech">
                        <!-- <span>I</span> -->
                        <span class="word">私</span>
                        <span class="fragment grow">I</span>
                    </span>
                    <span class="partofspeech">
                        <span class="word">は</span>
                        <span class="fragment grow">T.M.</span>
                    </span>
                    <span class="partofspeech">
                        <!-- <span>pizza</span> -->
                        <span class="word">ピザ</span>
                        <span class="fragment grow">Pizza</span>
                    </span>
                    <span class="partofspeech">
                        <span class="word">を</span>
                        <span class="fragment grow">D.O.M</span>
                    </span>
                    <span class="partofspeech">
                        <!-- <span>eat</span> -->
                        <span class="word">食べる</span>
                        <span class="fragment grow">Eat</span>
                    </span>
                </h2>
            </div>
        </section>
    </section>
</template>

<script>
export default {

}
</script>

<style scoped lang="stylus">
.word
{
    display: block
}
.partofspeech
{
    display: inline-block
}
.fragment
{
    text-decoration: overline
}
.current-fragment
    color blue
</style>
