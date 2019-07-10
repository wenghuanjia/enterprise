<template>
    <div class="t7">
        <table class="table table-hover table-bordered" v-loading="loading">
            <tbody>
                <tr>
                    <td colspan="6" align="center">知识产权管理</td>
                </tr>
                <tr>
                    <td>知识产权</td>
                    <td colspan="5">I类</td>
                </tr>
                <!-- 集成电路布线图 -->
                <tr>
                    <td>集成电路布线图</td>
                    <td>
                        <a target="_blank" v-if="text.text1['file']" download="file" :href="text.text1['file']['url']">{{ text.text1['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text1, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text2" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text3" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text4['file']" download="file" :href="text.text4['file']['url']">{{ text.text4['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text4, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text5['file']" download="file" :href="text.text5['file']['url']">{{ text.text5['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text5, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text6['file']" download="file" :href="text.text6['file']['url']">{{ text.text6['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text6, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text7['file']" download="file" :href="text.text7['file']['url']">{{ text.text7['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text7, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="6"></td>
                </tr>
                <!-- 发明专利 -->
                <tr>
                    <td>发明专利</td>
                    <td>
                        <a target="_blank" v-if="text.text8['file']" download="file" :href="text.text8['file']['url']">{{ text.text8['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text8, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text9" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text10" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text11['file']" download="file" :href="text.text11['file']['url']">{{ text.text11['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text11, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text12['file']" download="file" :href="text.text12['file']['url']">{{ text.text12['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text12, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text13['file']" download="file" :href="text.text13['file']['url']">{{ text.text13['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text13, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text14['file']" download="file" :href="text.text14['file']['url']">{{ text.text14['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text14, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="6"></td>
                </tr>
                <!-- 植物新品种 -->
                <tr>
                    <td>植物新品种</td>
                    <td>
                        <a target="_blank" v-if="text.text15['file']" download="file" :href="text.text15['file']['url']">{{ text.text15['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text15, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text16" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text17" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text18['file']" download="file" :href="text.text18['file']['url']">{{ text.text18['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text18, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text19['file']" download="file" :href="text.text19['file']['url']">{{ text.text19['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text19, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text20['file']" download="file" :href="text.text20['file']['url']">{{ text.text20['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text20, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text21['file']" download="file" :href="text.text21['file']['url']">{{ text.text21['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text21, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="6"></td>
                </tr>
                <!-- 国家新药 -->
                <tr>
                    <td>国家新药</td>
                    <td>
                        <a target="_blank" v-if="text.text22['file']" download="file" :href="text.text22['file']['url']">{{ text.text22['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text22, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text23" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text24" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text25['file']" download="file" :href="text.text25['file']['url']">{{ text.text25['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text25, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text26['file']" download="file" :href="text.text26['file']['url']">{{ text.text26['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text26, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text27['file']" download="file" :href="text.text27['file']['url']">{{ text.text27['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text27, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text28['file']" download="file" :href="text.text28['file']['url']">{{ text.text28['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text28, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="6"></td>
                </tr>
                <!-- 国家一级中药保护品种 -->
                <tr>
                    <td>国家一级中药保护品种</td>
                    <td>
                        <a target="_blank" v-if="text.text29['file']" download="file" :href="text.text29['file']['url']">{{ text.text29['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text29, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text30" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text31" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text32['file']" download="file" :href="text.text32['file']['url']">{{ text.text32['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text32, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text33['file']" download="file" :href="text.text33['file']['url']">{{ text.text33['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text33, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text34['file']" download="file" :href="text.text34['file']['url']">{{ text.text34['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text34, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text35['file']" download="file" :href="text.text35['file']['url']">{{ text.text35['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text35, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="6"></td>
                </tr>
                <!-- 知识产权II类 -->
                <tr>
                    <td>知识产权</td>
                    <td colspan="5">II类</td>
                </tr>
                <tr>
                    <td>实用新型专利</td>
                    <td>
                        <a target="_blank" v-if="text.text36['file']" download="file" :href="text.text36['file']['url']">{{ text.text36['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text36, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text37" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text38" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text39['file']" download="file" :href="text.text39['file']['url']">{{ text.text39['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text39, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text40['file']" download="file" :href="text.text40['file']['url']">{{ text.text40['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text40, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text41['file']" download="file" :href="text.text41['file']['url']">{{ text.text41['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text41, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text42['file']" download="file" :href="text.text42['file']['url']">{{ text.text42['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text42, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="6"></td>
                </tr>
                <!-- 软件著作权 -->
                <tr>
                    <td>软件著作权</td>
                    <td>
                        <a target="_blank" v-if="text.text43['file']" download="file" :href="text.text43['file']['url']">{{ text.text43['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text43, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text44" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text45" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text46['file']" download="file" :href="text.text46['file']['url']">{{ text.text46['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text46, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text47['file']" download="file" :href="text.text47['file']['url']">{{ text.text47['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text47, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text48['file']" download="file" :href="text.text48['file']['url']">{{ text.text48['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text48, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text49['file']" download="file" :href="text.text49['file']['url']">{{ text.text49['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text49, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="6"></td>
                </tr>
                <!-- 外观设计专利 -->
                <tr>
                    <td>外观设计专利</td>
                    <td>
                        <a target="_blank" v-if="text.text50['file']" download="file" :href="text.text50['file']['url']">{{ text.text50['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text50, $event)" />
                    </td>
                    <td>申请时间</td>
                    <td><input type="text" class="form-control" v-model="text.text51" placeholder="请输入"/></td>
                    <td>取得时间</td>
                    <td><input type="text" class="form-control" v-model="text.text52" placeholder="请输入"/></td>
                </tr>
                <tr>
                    <td>申请材料附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text53['file']" download="file" :href="text.text53['file']['url']">{{ text.text53['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text53, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>专利证书附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text54['file']" download="file" :href="text.text54['file']['url']">{{ text.text54['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text54, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>收据或发表附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text55['file']" download="file" :href="text.text55['file']['url']">{{ text.text55['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text55, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>其它附件</td>
                    <td colspan="5">
                        <a target="_blank" v-if="text.text56['file']" download="file" :href="text.text56['file']['url']">{{ text.text56['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text56, $event)" />
                    </td>
                </tr>
            </tbody>
        </table>
        
        <div v-if="audit_flag == 3">
            <p style="margin-bottom: 10px;">批注</p>
            <input type="text" class="form-control" placeholder="批注" v-model="pzhu" style="margin-bottom: 15px;">
        </div>
        <div v-if="audit_flag == 2">
            <p style="margin-bottom: 10px;">批注:{{ pzhu }}</p>
        </div>

        <el-button type="primary" size="mini" @click="upload_data" v-if="state_flag == 1">保存</el-button>
        <!-- <el-button type="primary" size="mini" @click="set_data" v-if="state_flag == 2">修改</el-button>
        <el-button type="primary" size="mini" @click="setpostil" v-if="audit_flag == 3">添加批注</el-button>
        <el-button type="primary" size="mini" v-if="deriveFlag" @click="derived_field">导出word</el-button> -->
        <el-button type="primary" size="mini" @click="set_data" v-if="state_flag == 2">修改</el-button>
        <el-button type="primary" size="mini" @click="derived_field" v-if="state_flag == 2">导出word</el-button>
    </div>
</template>

<script>
import { create, read, update, edit, index, upload } from "service/getData"
import { mapState, mapMutations } from "vuex"
import json from "jsonify"

export default {
    props: ['flag', 'deriveFlag'],
    data () {
        return {
            pzhu: '', // 批注
            id: null, // 修改需要的id
            loading: true, // 加载中
            biao_id: 49, // 第几个表
            text: {
                text1: {},
                text2: "",
                text3: "",
                text4: {},
                text5: {},
                text6: {},
                text7: {},
                text8: {},
                text9: "",
                text10: "",
                text11: {},
                text12: {},
                text13: {},
                text14: {},
                text15: {},
                text16: "",
                text17: "",
                text18: {},
                text19: {},
                text20: {},
                text21: {},
                text22: {},
                text23: "",
                text24: "",
                text25: {},
                text26: {},
                text27: {},
                text28: {},
                text29: {},
                text30: "",
                text31: "",
                text32: {},
                text33: {},
                text34: {},
                text35: {},
                text36: {},
                text37: "",
                text38: "",
                text39: {},
                text40: {},
                text41: {},
                text42: {},
                text43: {},
                text44: "",
                text45: "",
                text46: {},
                text47: {},
                text48: {},
                text49: {},
                text50: {},
                text51: "",
                text52: "",
                text53: {},
                text54: {},
                text55: {},
                text56: {},
            },
            pro_id: null, // 项目id
            project_type_id: "" // 项目类型id
        }
    },
    created () {
        this.project_type_id = this.$route.query.id; // 项目类型id
        this.pro_id = this.$route.query.pro_id ? this.$route.query.pro_id : null; // 项目id
        if (this.pro_id) {
            this.check_data();
        } else {
            this.loading = false;
        }
        // console.log(this.biao_id)
        // console.log(this.pro_id)
        // console.log(this.project_type_id)
    },
    computed: {
        ...mapState(['state_flag', 'audit_flag'])
    },
    methods: {
        // 上传附件
        addproof (aim, e) {
            // aim 传递过来提交目标
            // console.log(aim)
            if (e.target.files.length == 0) return;
            const loading = this.$loading({
                lock: true,
                text: '上传中',
                spinner: 'el-icon-loading',
                background: 'rgba(0, 0, 0, 0.7)'
            });

            var file = e.target.files;
            let param = new FormData();
            param.append('file', file[0]);
            upload(param).then(res => {
                loading.close();
                if (res.code == 1) {
                    this.$message.success(res.msg);
                    aim.file = res.data;
                } else {
                    this.$message.error(res.msg);
                }
            })
        },
        ...mapMutations(['SET_STATE_FLAG']),
        // 导出word
        derived_field () {
            index({
                biao_id: this.biao_id,
                pro_id: this.pro_id
            }).then(res => {
                window.open(res)
            })
        },
        // 添加批注
        setpostil () {
            const loading = this.$loading({
                lock: true,
                text: '上传中',
                spinner: 'el-icon-loading',
                background: 'rgba(0, 0, 0, 0.7)'
            });
            edit({
                biao_id: this.biao_id,
                id: this.id,
                pzhu: this.pzhu
            }).then(res => {
                loading.close();
            }).catch(err => {
                loading.close();
            })
        },
        // 查询表数据
        check_data () {
            var data = {pro_id: this.pro_id,biao_id: this.biao_id}
            read(data).then(res => {
                // console.log(res)
                this.$emit('hide_table', res.showArr);
                if (res.data.length >= 1) {
                    var data = res.data[0]['content'];
                    Object.keys(data).forEach(key => {
                        this[key] = data[key]
                    })
                    if (typeof res.data[0]['content']['text'] != 'object') {
                        this.text = json.parse(res.data[0]['content']['text'])
                    }
                    this.id = res.data[0].id;
                    this.pro_id = res.data[0].pro_id;
                    this.pzhu = res.data[0].pzhu;
                    this.SET_STATE_FLAG(2); // 修改
                } else {
                    this.SET_STATE_FLAG(1); // 添加
                }
                if (this.flag) { // 查看
                    this.SET_STATE_FLAG(3);
                }
                this.loading = false;
            })
        },
        // 添加一行数据
        add_text (text) {
            var len = 1;
            for (var event in this[text]) {
                len++;
            }
            this.$set(this[text], `text${len}`, {});
        },
        // 修改表数据
        set_data () {
            const loading = this.$loading({
                lock: true,
                text: '上传中',
                spinner: 'el-icon-loading',
                background: 'rgba(0, 0, 0, 0.7)'
            });
            var data = {
                text: this.text,
                biao_id: this.biao_id, // 第几个表
                id: this.id, // 项目id
            }
            // data = json.stringify(data)
            update(data).then(res => {
                loading.close();
                this.$message.success('修改成功!');
            }).catch(err => {
                loading.close();
            });
        },
        // 添加表数据
        upload_data () {
            const loading = this.$loading({
                lock: true,
                text: '上传中',
                spinner: 'el-icon-loading',
                background: 'rgba(0, 0, 0, 0.7)'
            });
            var data = {
                // text1: this.text1,
                // text2: this.text2,
                // text3: this.text3,
                // text4: this.text4,
                // text5: this.text5,
                // text6: this.text6,
                // text7: this.text7,
                // text8: this.text8,
                // text9: this.text9,
                // text10: this.text10,
                // text11: this.text11,
                // text12: this.text12,
                // text13: this.text13,
                // text14: this.text14,
                // text15: this.text15,
                // text16: this.text16,
                // text17: this.text17,
                // text18: this.text18,
                // text19: this.text19,
                // text20: this.text20,
                // text21: this.text21,
                // text22: this.text22,
                // text23: this.text23,
                // text24: this.text24,
                // text25: this.text25,
                text: this.text,
                biao_id: this.biao_id, // 第几个表
                pro_id: this.pro_id, // 项目id
                project_type_id: this.project_type_id // 项目类型id
            }
            // data = json.stringify(data)
            create(data).then(res => {
                loading.close();
                this.$message.success('上传成功!');
                this.id = res.id;
                this.SET_STATE_FLAG(2);
                // 第一次添加有pro_id
                if (res.pro_id) {
                    this.$router.push({query: {'id': this.project_type_id, 'pro_id':res.pro_id}})
                }
            }).catch(err => {
                loading.close();
            })
        }
    }
}
</script>

<style scoped lang="less">
    .form-inlin {
        display: inline-block;
        width: 200px;
    }

    input[type="radio"] {
        -webkit-appearance: radio;
        margin: 0px;
    }

    input[type="checkbox"] {
        -webkit-appearance: checkbox;
        margin: 0px;
    }

    .title {
        text-align: center;
    }
</style>
