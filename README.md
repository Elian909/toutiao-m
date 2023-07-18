module.exports = {
    // 配置要使用的 PostCSS 插件
    plugins: {
        // 配置使用 autoprefixer 插件
        // 作用：生成浏览器 CSS 样式规则前缀
        // VueCLI 内部已经配置了 autoprefixer 插件
        // 所以又配置了一次，所以产生冲突了
        // 'autoprefixer': { // autoprefixer 插件的配置
        //   // 配置要兼容到的环境信息
        //   browsers: ['Android >= 4.0', 'iOS >= 8']
        // },

        // 配置使用 postcss-pxtorem 插件
        // 作用：把 px 转为 rem
        'postcss-pxtorem': {
            //lib-flexible 的rem适配方案：把一行分为十份，每一份是1/10
            //但vant建议设计成37.5 为什么？因为vant基于375 ，唯一的缺点是设计稿要除以2
            //通过查阅，rootValue有两种类型：
            //1.数字：固定的数值
            //2.函数：返回一个数值，这个数值会作为根值
            //postcss-pxtorem 处理每个css文件时都会调用这个函数，他会把被处理的css文件相关的信息通过参数传递给该函数
            //这里我们使用第二种方式
            rootValue({ file }) {
                return file.indexOf('vant') !== -1 ? 37.5 : 75
            },
            //配备要转换的css属性
            //* 所有
            propList: ['*']
        }
    }
}

