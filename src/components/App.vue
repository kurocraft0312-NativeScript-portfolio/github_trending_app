<template>
    <Page>
        <ActionBar title="GitHub_Trending_App" android:flat="true"/>
        <TabView android:tabBackgroundColor="#53ba82"
                 android:tabTextColor="#c4ffdf"
                 android:selectedTabTextColor="#ffffff"
                 androidSelectedTabHighlightColor="#ffffff">
            <TabViewItem title="Today">
                <GridLayout columns="*" rows="*">
                    <Label class="message" :text="msg" col="0" row="0"/>
                </GridLayout>
            </TabViewItem>
            <TabViewItem title="Weekly">
                <GridLayout columns="*" rows="*">
                    <Label class="message" text="Tab 91 Content" col="0" row="0"/>
                </GridLayout>
            </TabViewItem>
            <TabViewItem title="Monthly">
                <GridLayout columns="*" rows="*">
                    <Label class="message" text="Tab 3 Content" col="0" row="0"/>
                </GridLayout>
            </TabViewItem>
        </TabView>
    </Page>
</template>

<script lang="ts">
    import axios, { AxiosRequestConfig } from 'axios/dist/axios'
    export default {
        data() {
            return {
                msg: 'Hello World!',
                }
        },
        methods: {
            async apireq(): Promise<AxiosRequestConfig> {
                    const res: AxiosRequestConfig = await axios.get('https://github-trending-api.waningflow.com/repositories');
                    console.log(res.data);
                    return res;
                }
        }
    }
</script>

<style scoped>
    ActionBar {
        background-color: #53ba82;
        color: #ffffff;
    }

    .message {
        vertical-align: center;
        text-align: center;
        font-size: 20;
        color: #333333;
    }
</style>
