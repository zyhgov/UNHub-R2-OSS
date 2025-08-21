<template>
  <footer class="footer">


    <div class="stats">
      <p id="running-time">网站运行时间加载中...</p>
    </div>

    <div class="project-links">
      <strong>项目:</strong><a href="https://github.com/zyhgov/UNHub-R2-OSS" target="_blank"
        rel="noopener noreferrer">UNHub-R2-OSS</a>
      <strong>支持:</strong><a href="https://www.cloudflare-cn.com/enterprise/" target="_blank"
        rel="noopener noreferrer">Cloudflare</a>
    </div>

    <div class="powered">Powered by <a href="https://workers.cloudflare.com/" target="_blank"
        rel="noopener noreferrer">Cloudflare Workers</a></div>

    <div style="margin:10px 0;">© 2025 UNHub R2 OSS. All rights reserved.</div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      homeUrl: "https://zyhgov.cn/",
      blogUrl: "https://zyhorg.ac.cn/globalnews.html",
      githubUrl: "https://github.com/zyhgov",
      emailUrl: "mailto:info@zyhorg.cn"
    };
  }
};

const startDate = new Date('2025-06-24T00:00:00').getTime();

function updateRunningTime() {
    const now = new Date().getTime();
    const diff = now - startDate;

    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((diff % (1000 * 60)) / 1000);

    document.getElementById('running-time').textContent =
        `平稳运行 : ${days} 天 ${hours} 时 ${minutes} 分 ${seconds} 秒`;
}

updateRunningTime();

setInterval(updateRunningTime, 1000);
</script>


<style scoped>
.footer {
  margin-top: 30px;
  text-align: center;
  padding: 20px;
  background-color: #ffffff77;
  font-size: 16px;
  border-radius: 50% 50% 0 0;

}

.icons {
  display: flex;
  justify-content: center;
  gap: 16px;
  margin-bottom: 25px;
}

.icon-link {
  width: 28px;
  height: 28px;
  display: inline-block;
  fill: #2c2c2c;
  transition: fill 0.3s;
}

.icon-link:hover {
  fill: #444;
}

.stats {
  margin: 10px 0;
  color: #444;
}

.project-links {
  font-size: 14px;
  color: #444;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 15px;
  text-align: center;
}

.project-links a {
  color: #444;
  text-decoration: none;
}

.project-links a:hover {
  color: #222;
}

.powered {
  margin-top: 10px;
  color: #444;
}

.powered a {
  color: #444;
  text-decoration: none;
}

.powered a:hover {
  color: #222;
}
</style>
