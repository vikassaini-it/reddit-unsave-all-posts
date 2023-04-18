# reddit-unsave-all-posts
Unsave all post reddit



Open page after logging in: https://www.reddit.com/user/{username}/saved/

Open console and paste this script:


const delay = (ms) => new Promise((res) => setTimeout(res, ms));


```const execute = async (arr) => {
  for (const el of arr) {
    if (el.innerText === "unsave") {
      el.click();
      await delay(500);
      console.log("delete requested");
    }
  }
};

const start = async () => {
  while (1) {
    const arr = Array.from(document.querySelectorAll("button"));
    await execute(arr);
    window.scrollTo(0, document.body.scrollHeight);
    await delay(5000);
  }
};

(async () => {
  await start();
})();
