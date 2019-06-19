<template>
    <div class="t7">
        <table class="table table-hover table-bordered" v-loading="loading">
            <tbody>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <tr>
                    <td colspan="5" align="center">高新材料收集管理</td>
                </tr>
                <!-- 证明企业依法成立的相关注册登记证件 -->
                <tr>
                    <td>证明企业依法成立的相关注册登记证件</td>
                    <td colspan="4">
                        <a target="_blank" v-if="text.text1['file']" download="file" :href="text.text1['file']['url']">{{ text.text1['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text1, $event)" />
                    </td>
                </tr>
                <!-- 企业营业执照 -->
                <tr>
                    <td rowspan="2">企业营业执照</td>
                    <td>企业营业执照正本(上传附件)</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text2['file']" download="file" :href="text.text2['file']['url']">{{ text.text2['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text2, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>企业营业执照副本(上传附件)</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text3['file']" download="file" :href="text.text3['file']['url']">{{ text.text3['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text3, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 上一年度... -->
                <tr>
                    <td rowspan="5" width="400px">上一年度3月份、6月份、9月份、12月份共4个月份的个人所得税缴纳人数汇总数截图或社保缴纳人数证明材料(只需汇总数，加盖企业公章)，本企业科技人员名单及其工作岗位等</td>
                    <td>3月份个人所得税缴纳人数汇总数截图或社保缴纳人数证明材料</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text4['file']" download="file" :href="text.text4['file']['url']">{{ text.text4['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text4, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>6月个人所得税缴纳人数汇总数截图或社保缴纳人数证明材料</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text5['file']" download="file" :href="text.text5['file']['url']">{{ text.text5['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text5, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>9月个人所得税缴纳人数汇总数截图或社保缴纳人数证明材料</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text6['file']" download="file" :href="text.text6['file']['url']">{{ text.text6['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text6, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>12月个人所得税缴纳人数汇总数截图或社保缴纳人数证明材料</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text7['file']" download="file" :href="text.text7['file']['url']">{{ text.text7['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text7, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>企业科技人员名单及其工作岗位</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text8['file']" download="file" :href="text.text8['file']['url']">{{ text.text8['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text8, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 盖有主管税务机关受理章的近三年企业所得税年度纳税申报表主表及附表的复印件（实际年限不足3年的按实际经营年限） -->
                <tr>
                    <td rowspan="3">盖有主管税务机关受理章的近三年企业所得税年度纳税申报表主表及附表的复印件（实际年限不足3年的按实际经营年限）</td>
                    <td>近第一年企业所得税年度纳税申报表主表及附表</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text9['file']" download="file" :href="text.text9['file']['url']">{{ text.text9['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text9, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第二年企业所得税年度纳税申报表主表及附表</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text10['file']" download="file" :href="text.text10['file']['url']">{{ text.text10['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text10, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第三年企业所得税年度纳税申报表主表及附表</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text11['file']" download="file" :href="text.text11['file']['url']">{{ text.text11['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text11, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 经具有资质的... -->
                <tr>
                    <td rowspan="3">经具有资质的中介机构鉴证的企业年三年年度的财务审计报告（含资产负债表、利润及利润分配表、现金流量表、附注和财务情况说明书，实际年限不足3年的按实际经营年限</td>
                    <td>近第一年年度的财务审计报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text12['file']" download="file" :href="text.text12['file']['url']">{{ text.text12['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text12, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第二年年度的财务审计报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text13['file']" download="file" :href="text.text13['file']['url']">{{ text.text13['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text13, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第三年年度的财务审计报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text14['file']" download="file" :href="text.text14['file']['url']">{{ text.text14['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text14, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 经具有资质并符合... -->
                <tr>
                    <td rowspan="3">经具有资质并符合《工作指引》相关条件的中介机构（企业自行选择符合要求的中介机构）鉴证的企业近三年年度研究开发费用专项审计报告（经营不足3年的企业，按实际年度出具审计报告）和2018年高新技术产品（服务）收入的专项审计报告。</td>
                    <td>近三年度研究开发费用专项审计报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text15['file']" download="file" :href="text.text15['file']['url']">{{ text.text15['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text15, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近一年高新技术产品（服务）收入的专项审计报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text16['file']" download="file" :href="text.text16['file']['url']">{{ text.text16['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text16, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="4"></td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 研究开发活动材料：项目名称、项目组成员、项目立项报告、中期检查报告、结题验收报告等... -->
                <tr>
                    <td rowspan="3">研究开发活动材料：项目名称、项目组成员、项目立项报告、中期检查报告、结题验收报告等</td>
                    <td>近第三年项目报告（建议每年3个以上立项）</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text17['file']" download="file" :href="text.text17['file']['url']">{{ text.text17['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text17, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第三年项目报告（建议每年3个以上立项）</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text18['file']" download="file" :href="text.text18['file']['url']">{{ text.text18['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text18, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第三年项目报告（建议每年3个以上立项）</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text19['file']" download="file" :href="text.text19['file']['url']">{{ text.text19['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text19, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 有效知识产权材料... -->
                <tr>
                    <td rowspan="14">有效知识产权材料：知识产权授权证书或授权通知书及缴费收据；国家知识产权局等官方网站上公布的摘要，通过转让、受赠、并购取得的知识产权需提供相关主管机关出具的变更证明等材料。知识产权有多个权属人时，需提供其他权属人同意该企业使用本知识产权申报高新技术企业的声明，所有权属人需加盖公章。企业以前年度认定高企时所填报使用的Ⅱ类知识产权，不能再次填报。</td>
                    <td rowspan="10">知识产权授权证书或授权通知书及缴费收据</td>
                    <td>I类</td>
                    <td>集成电路布线图</td>
                    <td>
                        <a target="_blank" v-if="text.text20['file']" download="file" :href="text.text20['file']['url']">{{ text.text20['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text20, $event)" />
                    </td>
                </tr>
                <tr>
                    <td></td>
                    <td>发明专利</td>
                    <td>
                        <a target="_blank" v-if="text.text21['file']" download="file" :href="text.text21['file']['url']">{{ text.text21['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text21, $event)" />
                    </td>
                </tr>
                <tr>
                    <td></td>
                    <td>植物新品种</td>
                    <td>
                        <a target="_blank" v-if="text.text22['file']" download="file" :href="text.text22['file']['url']">{{ text.text22['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text22, $event)" />
                    </td>
                </tr>
                <tr>
                    <td></td>
                    <td>国家级农作物品种</td>
                    <td>
                        <a target="_blank" v-if="text.text23['file']" download="file" :href="text.text23['file']['url']">{{ text.text23['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text23, $event)" />
                    </td>
                </tr>
                <tr>
                    <td></td>
                    <td>国家新药</td>
                    <td>
                        <a target="_blank" v-if="text.text24['file']" download="file" :href="text.text24['file']['url']">{{ text.text24['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text24, $event)" />
                    </td>
                </tr>
                <tr>
                    <td></td>
                    <td>国家一级中药保护品种</td>
                    <td>
                        <a target="_blank" v-if="text.text25['file']" download="file" :href="text.text25['file']['url']">{{ text.text25['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text25, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="3"></td>
                </tr>
                <tr>
                    <td>II类</td>
                    <td>使用新型专利</td>
                    <td>
                        <a target="_blank" v-if="text.text26['file']" download="file" :href="text.text26['file']['url']">{{ text.text26['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text26, $event)" />
                    </td>
                </tr>
                <tr>
                    <td></td>
                    <td>软件著作权</td>
                    <td>
                        <a target="_blank" v-if="text.text27['file']" download="file" :href="text.text27['file']['url']">{{ text.text27['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text27, $event)" />
                    </td>
                </tr>
                <tr>
                    <td></td>
                    <td>外观设计专利</td>
                    <td>
                        <a target="_blank" v-if="text.text28['file']" download="file" :href="text.text28['file']['url']">{{ text.text28['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text28, $event)" />
                    </td>
                </tr>
                <tr>
                    <td rowspan="2" width="350px">国家知识产权局等官方网站上公布的摘要，通过转让、受赠、并购取得的知识产权需提供相关主管机关出具的变更证明等材料</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text29['file']" download="file" :href="text.text29['file']['url']">{{ text.text29['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text29, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="3"></td>
                </tr>
                <tr>
                    <td rowspan="2">知识产权有多个权属人时，需提供其他权属人同意该企业使用本知识产权申报高新技术企业的声明，所有权属人需加盖公章。</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text30['file']" download="file" :href="text.text30['file']['url']">{{ text.text30['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text30, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="3"></td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 科技成果转化证明材料 -->
                <tr>
                    <td rowspan="17">科技成果转化证明材料：成果来源可从专利、技术诀窍、项目立项证明等方面提供证明材料；转化结果可从生产批文、新产品或新技术推广应用证明、产品质量检验报告等方面提供材料。</td>
                    <td>近一年合同（建议6份以上）</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text31['file']" download="file" :href="text.text31['file']['url']">{{ text.text31['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text31, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>生产批文</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text32['file']" download="file" :href="text.text32['file']['url']">{{ text.text32['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text32, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>新产品</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text33['file']" download="file" :href="text.text33['file']['url']">{{ text.text33['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text33, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>新技术推广应用证明</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text34['file']" download="file" :href="text.text34['file']['url']">{{ text.text34['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text34, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>产品质量检验报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text35['file']" download="file" :href="text.text35['file']['url']">{{ text.text35['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text35, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="4"></td>
                </tr>
                <tr>
                    <td>近二年合同（建议6份）</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text36['file']" download="file" :href="text.text36['file']['url']">{{ text.text36['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text36, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>生产批文</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text37['file']" download="file" :href="text.text37['file']['url']">{{ text.text37['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text37, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>新产品</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text38['file']" download="file" :href="text.text38['file']['url']">{{ text.text38['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text38, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>新技术推广应用证明</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text39['file']" download="file" :href="text.text39['file']['url']">{{ text.text39['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text39, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>产品质量检验报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text40['file']" download="file" :href="text.text40['file']['url']">{{ text.text40['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text40, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="4">
                    </td>
                </tr>
                <tr>
                    <td>近三年合同（建议6份以上）</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text41['file']" download="file" :href="text.text41['file']['url']">{{ text.text41['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text41, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>生产批文</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text42['file']" download="file" :href="text.text42['file']['url']">{{ text.text42['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text42, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>新产品</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text43['file']" download="file" :href="text.text43['file']['url']">{{ text.text43['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text43, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>新技术推广应用证明</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text44['file']" download="file" :href="text.text44['file']['url']">{{ text.text44['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text44, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>产品质量检验报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text45['file']" download="file" :href="text.text45['file']['url']">{{ text.text45['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text45, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 研发组织管理水平... -->
                <tr>
                    <td rowspan="13">研发组织管理水平材料：研发组织管理制度、研发投入核算体系；研发机构建设及设备设施、开展产学研合作活动；成果转化的组织实施与激励奖励制度、创新创业平台建立情况；科技人员的培养进修、职工技能培训、优秀人才引进，及人才绩效评价奖励制度等材料。</td>
                    <td>研发组织管理制度</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text46['file']" download="file" :href="text.text46['file']['url']">{{ text.text46['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text46, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>研发投入核算体系</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text47['file']" download="file" :href="text.text47['file']['url']">{{ text.text47['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text47, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第一年研发费用台账</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text48['file']" download="file" :href="text.text48['file']['url']">{{ text.text48['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text48, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第二年研发费用台账</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text49['file']" download="file" :href="text.text49['file']['url']">{{ text.text49['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text49, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>近第三年研发费用台账</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text50['file']" download="file" :href="text.text50['file']['url']">{{ text.text50['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text50, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>研发机构建设及设备设施</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text51['file']" download="file" :href="text.text51['file']['url']">{{ text.text51['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text51, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>研发部架构图</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text52['file']" download="file" :href="text.text52['file']['url']">{{ text.text52['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text52, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>开展产学研合作活动</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text53['file']" download="file" :href="text.text53['file']['url']">{{ text.text53['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text53, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>成果转化的组织实施与激励奖励制度</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text54['file']" download="file" :href="text.text54['file']['url']">{{ text.text54['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text54, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>奖励证明</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text55['file']" download="file" :href="text.text55['file']['url']">{{ text.text55['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text55, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>创新创业平台建立情况</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text56['file']" download="file" :href="text.text56['file']['url']">{{ text.text56['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text56, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>科技人员的培养进修、职工技能培训、优秀人才引进，及人才绩效评价奖励制度</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text57['file']" download="file" :href="text.text57['file']['url']">{{ text.text57['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text57, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>奖励证明</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text58['file']" download="file" :href="text.text58['file']['url']">{{ text.text58['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text58, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 企业高新技术产品... -->
                <tr>
                    <td rowspan="5">企业高新技术产品（服务）材料：判断该产品（服务）为高新技术产品（服务）的依据及理由、高新技术产品的核心技术情况、产品指标及在同行业的先进性、是否为主要高新技术产品等材料。</td>
                    <td>高新技术产品证书</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text59['file']" download="file" :href="text.text59['file']['url']">{{ text.text59['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text59, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>知识产权证书</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text60['file']" download="file" :href="text.text60['file']['url']">{{ text.text60['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text60, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>查新报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text61['file']" download="file" :href="text.text61['file']['url']">{{ text.text61['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text61, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>鉴定证书</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text62['file']" download="file" :href="text.text62['file']['url']">{{ text.text62['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text62, $event)" />
                    </td>
                </tr>
                <tr>
                    <td>检测或检验报告</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text63['file']" download="file" :href="text.text63['file']['url']">{{ text.text63['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text63, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="5"></td>
                </tr>
                <!-- 出具企业研发费用 -->
                <tr>
                    <td rowspan="2">出具企业研发费用、高新技术产品（服务）收入专项审计的中介机构应提供营业执照（复印件）、执业证书复印件、全年月职工平均人数、注册会计师人数等相关证明材料，作为附件附在专项审计报告后。</td>
                    <td>中介机构应提供营业执照（复印件）、执业证书复印件、全年月职工平均人数、注册会计师人数等相关证明材料</td>
                    <td colspan="3">
                        <a target="_blank" v-if="text.text64['file']" download="file" :href="text.text64['file']['url']">{{ text.text64['file']['filename'] }}</a>
                        <input type="file" @change="addproof(text.text64, $event)" />
                    </td>
                </tr>
                <tr>
                    <td colspan="4"></td>
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
            biao_id: 50, // 第几个表
            text: {
                text1: {},
                text2: {},
                text3: {},
                text4: {},
                text5: {},
                text6: {},
                text7: {},
                text8: {},
                text9: {},
                text10: {},
                text11: {},
                text12: {},
                text13: {},
                text14: {},
                text15: {},
                text16: {},
                text17: {},
                text18: {},
                text19: {},
                text20: {},
                text21: {},
                text22: {},
                text23: {},
                text24: {},
                text25: {},
                text26: {},
                text27: {},
                text28: {},
                text29: {},
                text30: {},
                text31: {},
                text32: {},
                text33: {},
                text34: {},
                text35: {},
                text36: {},
                text37: {},
                text38: {},
                text39: {},
                text40: {},
                text41: {},
                text42: {},
                text43: {},
                text44: {},
                text45: {},
                text46: {},
                text47: {},
                text48: {},
                text49: {},
                text50: {},
                text51: {},
                text52: {},
                text53: {},
                text54: {},
                text55: {},
                text56: {},
                text57: {},
                text58: {},
                text59: {},
                text60: {},
                text61: {},
                text62: {},
                text63: {},
                text64: {},
            },
            // text11: {text1:{}},
            // text12: {text1:{}},
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
    },
    computed: {
        ...mapState(['state_flag', 'audit_flag'])
    },
    methods: {
        // 上传附件
        addproof (aim, e) {
            // aim 传递过来提交目标
            console.log(aim)
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
            read({pro_id: this.pro_id,biao_id: this.biao_id}).then(res => {
                console.log(res)
                this.$emit('hide_table', res.showArr);
                if (res.data.length >= 1) {
                    var data = res.data[0]['content'];
                    Object.keys(data).forEach(key => {
                        this[key] = data[key]
                    })
                    // this.text = json.parse(res.data[0]['content']['text']);
                    if (typeof res.data[0]['content']['text'] != 'object') {
                        this.text = json.parse(res.data[0]['content']['text']);
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
            update({
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
                id: this.id, // 项目id
            }).then(res => {
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
