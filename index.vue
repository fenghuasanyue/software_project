<template>
  <div class="app-container home">
    <el-row :gutter="20">
      <el-col :span="24">
        <el-card class="glass-card welcome-card">
          <h1 class="main-title">计算机学院专属数据中台</h1>
          <p class="sub-title">
            本项目旨在解决工程认证及日常行政评估中，学院跨部门数据（科研、教学、学工）收集存在的困难。通过建立统一的平台，替代低效的人工催收流程，实现数据的集中沉淀、流转与可视化展示。系统致力于减轻学院教职工的工作负担，优化各角色的操作体验，确保各级领导与教师能清晰预见数字化办公的高效场景。
          </p>

          <div class="action-group">
            <el-tag effect="dark" color="#8ec5fc" style="border: none;">学院专属</el-tag>
            <el-tag effect="dark" color="#e0c3fc" style="border: none; margin-left: 10px;">数据驱动</el-tag>

            <el-divider direction="vertical" class="custom-divider"></el-divider>

            <el-button type="primary" size="medium" icon="el-icon-s-data" round @click="goToDashboard">
              进入领导驾驶舱
            </el-button>
            <el-button size="medium" icon="el-icon-document" round plain @click="goToGuide">
              操作指南
            </el-button>
          </div>
        </el-card>
      </el-col>
    </el-row>

    <el-row :gutter="20" class="info-section">
      <el-col :xs="24" :sm="12">
        <el-card class="glass-card info-card">
          <div slot="header" class="card-header">
            <span><i class="el-icon-s-custom"></i> 核心职责说明</span>
          </div>
          <div class="body">
            <p><i class="el-icon-user"></i> <b>学院领导 (UR01)：</b>宏观数据决策与可视化大屏查看。</p>
            <p><i class="el-icon-s-check"></i> <b>部门管理员 (UR02)：</b>数据审核、Excel批量导入与管理。</p>
            <p><i class="el-icon-edit-outline"></i> <b>一线教师 (UR03)：</b>基础数据录入、修改与个人查询。</p>
            <p><i class="el-icon-setting"></i> <b>系统管理员 (UR04)：</b>系统底层运维、权限配置与安全审计。</p>
          </div>
        </el-card>
      </el-col>

      <el-col :xs="24" :sm="12">
        <el-card class="glass-card info-card">
          <div slot="header" class="card-header">
            <span><i class="el-icon-shield"></i> 系统性能标准</span>
          </div>
          <div class="body">
            <p><i class="el-icon-time"></i> <b>响应时间：</b>常规查询 ≤ 2s，报表生成与大屏首次加载 ≤ 5s。</p>
            <p><i class="el-icon-data-line"></i> <b>并发承载：</b>专项优化，支持至少 100 名教师同时在线填报不卡顿。</p>
            <p><i class="el-icon-lock"></i> <b>安全等级：</b>高敏隐私数据 AES 算法加密，越权行为自动记录拦截日志。</p>
          </div>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "Index",
  data() {
    return {};
  },
  methods: {
    goToDashboard() {
      this.$message.info("大屏模块正在开发中...");
    },
    goToGuide() {
      this.$message.info("操作指南完善中...");
    }
  }
};
</script>

<style scoped lang="scss">
.app-container.home {
  /* 背景渐变：从浅紫色过渡到淡蓝色 */
  background: linear-gradient(135deg, #e0c3fc 0%, #8ec5fc 100%);
  min-height: calc(100vh - 84px);
  padding: 30px;
  overflow-x: hidden;
  font-family: "Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", Arial, sans-serif;
  color: #333;

  /* 通用毛玻璃卡片样式 */
  ::v-deep .glass-card {
    background-color: rgba(255, 255, 255, 0.7) !important;
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    border: 1px solid rgba(255, 255, 255, 0.5);
    border-radius: 12px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
  }

  /* 顶部大卡片专属样式 */
  .welcome-card {
    padding: 20px 30px;
    margin-bottom: 25px;

    .main-title {
      font-size: 30px;
      font-weight: 600;
      color: #2c3e50;
      margin-top: 0;
      margin-bottom: 20px;
      letter-spacing: 1px;
    }

    .sub-title {
      font-size: 15px;
      line-height: 1.8;
      color: #5a6e82;
      margin-bottom: 30px;
      text-align: justify;
    }

    /* 标签和按钮排成整齐的一行 */
    .action-group {
      display: flex;
      align-items: center;

      .custom-divider {
        height: 24px;
        margin: 0 20px;
        background-color: #dcdfe6;
      }

      .el-button {
        font-weight: bold;
        letter-spacing: 1px;
      }
    }
  }

  /* 底部卡片专属样式 */
  .info-section {
    .info-card {
      height: 100%;

      .card-header {
        font-size: 16px;
        font-weight: bold;
        color: #2c3e50;
        i {
          margin-right: 8px;
          color: #409EFF;
        }
      }

      .body p {
        margin-bottom: 18px;
        line-height: 1.6;
        font-size: 14px;
        color: #475669;

        &:last-child {
          margin-bottom: 0;
        }

        b {
          color: #2c3e50;
        }

        i {
          margin-right: 5px;
          color: #909399;
        }
      }
    }
  }

  /* 消除卡片头部默认的生硬下划线 */
  ::v-deep .el-card__header {
    border-bottom: 1px solid rgba(0, 0, 0, 0.05);
    padding: 20px 25px;
  }
  ::v-deep .el-card__body {
    padding: 20px 25px;
  }
}
</style>
