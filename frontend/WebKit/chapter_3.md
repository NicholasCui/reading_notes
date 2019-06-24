#  第三章 WebKit 架构和模块

WebKit 架构：

<table style="text-align:center;">
    <tr>
        <td style="border:1px solid;">
            <table style="margin: 3px;text-align:center;">
                <tr>
                    <td colspan="4" style="border: 1px dashed" width="50%">
                        WebKit 嵌入式接口
                    </td>
                    <td colspan="4" style="border: 1px dashed" width="50%">
                        WebKit2 嵌入式接口
                    </td>
                </tr>
                <tr>
                    <td colspan="4" style="border: 1px dashed">
                        WebKit 绑定
                    </td>
                    <td colspan="4" style="border: 1px dashed">
                        WebKit2 绑定
                    </td>
                </tr>
            </table>
        </td>
    </tr>
    <tr>
        <td style="border:1px solid;">
            <table style="margin: 3px;text-align:center;">
                <tr>
                    <td width="50%">
                        <table style="text-align:center;">
                            <tr>
                            	<td colspan="4" style="border:1px solid">
                                	WebCore
                                </td>
                            </tr>
                            <tr>
                            	<td style="border:1px solid">
                                    CSS
                                </td>
                                <td style="border:1px solid">
                                    SVG
                                </td>
                                <td style="border:1px solid">
                                    布局
                                </td>
                                <td style="border:1px solid">
                                    渲染树
                                </td>
                            </tr>
                            <tr>
                            	<td style="border:1px solid">
                                    HTML
                                </td>
                                <td style="border:1px solid">
                                    DOM
                                </td>
                                <td style="border:1px solid">
                                    Inspector
                                </td>
                                <td style="border:1px solid">
                                    ...
                                </td>
                            </tr>
                        </table>
                    </td>
                    <td style="border: 1px dashed" width="50%">
                        <table style="text-align:center;">
                            <tr>
                                <td rowspan="3" style="border: 1px dashed">
                                    <p style="writing-mode: vertical-rl;">
                                        JavaScriptCore
                                    </p>
                                </td>
                            	<td colspan="3" style="border: 1px dashed">
                                	WebKit Ports
                                </td>
                            </tr>
                            <tr>
                                <td style="border: 1px dashed">
                                    网络栈
                                </td>
                                <td style="border: 1px dashed">
                                    网络栈
                                </td>
                                <td style="border: 1px dashed">
                                    网络栈
                                </td>
                            </tr>
                            <tr>
                                <td style="border: 1px dashed">
                                    硬件加速
                                </td>
                                <td style="border: 1px dashed">
                                    图片解码
                                </td>
                                <td style="border: 1px dashed">
                                    ...
                                </td>	
                            </tr>
                        </table>
                    </td>
                </tr>
                <tr>
                    <td colspan="2">
                        WebKit
                    </td>
                </tr>
            </table>
        </td>
    </tr>
</table>

<table style="text-align:center;">
    <tr>
        <td style="border: 1px dashed">
            2D 图形库
        </td>
        <td style="border: 1px dashed">
            3D 图形库
        </td>
        <td style="border: 1px dashed">
            网络库
        </td>
        <td style="border: 1px dashed">
            存储
        </td>
        <td style="border: 1px dashed">
            音频库
        </td>
        <td style="border: 1px dashed">
            视频库
        </td>
        <td style="border: 1px dashed">
            ...
        </td>
    </tr>
    <tr style="border: 1px dashed;margin-top:3px;">
        <td colspan="7" style="border: 1px dashed">
            操作系统
        </td>
    </tr>
</table>

虚线框表示该部分模块在不同浏览器使用的的WebKit内核中实现是不一样的，实线框表示它们是基本共享的。

