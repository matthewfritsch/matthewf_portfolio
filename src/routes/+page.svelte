<script lang='ts'>
    let time: string;
    let response_time: string;
    // Create a function to update the time
    function updateTime() {
        const date = new Date();
        const options: obj = {
            hour: '2-digit',
            minute: '2-digit',
            timeZone: 'America/Los_Angeles',
            hour12: true
        };
        time = new Intl.DateTimeFormat('en-US', options).format(date);
        email_response_time(date);
    }

    function email_response_time(date: Date) {
        const options: obj = {
            hour: '2-digit',
            minute: '2-digit',
            timeZone: 'America/Los_Angeles',
            hour12: false
        }
        let mil_time: string = new Intl.DateTimeFormat('en-US', options).format(date);
        let split: Array<string> = mil_time.split(':');
        if (Number(split[0]) > 20 || Number(split[0]) < 9) {
            response_time = "as soon as I can."
            return;
        }
        response_time = "shortly."
    }

    updateTime();
    setInterval(updateTime, 60 * 1000);
</script>

<div class="flex justify-center items-center mx-auto my-12 md:my-24 p-4">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4 items-center">
        <img class="mx-auto card max-h-72 md:max-h-none" src="matthewfritsch.png" alt="matthew fritsch" />
        <div class="mx-auto flex flex-col items-center p-6">
            <h1 class="h2 lg:h1 my-2">Matthew Fritsch</h1>
            <h3 class="h4 lg:h3 my-2">Backend Software Engineer</h3>
        </div>
    </div>
</div>

<div class="flex flex-col justify-center items-center mx-auto my-48 md:my-64 p-4">
    <h3 class="h1 my-4">About Me</h3>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4 items-center">
        <div class="flex flex-col items-center card p-4 divide-y divide-dashed">
            <header class="card-header">
                <h3 class="h3">I'm Currently Learning</h3>
            </header>
            <section class="flex flex-col items-center p-4 max-w-xs">
                <!-- ... -->
                <dl class="list-dl flex flex-col items-start">
                    <div>
                        <span class="badge bg-secondary-500">OpenGL</span>
                        <span class="flex-auto">
                            <dt>Graphics Programming</dt>
                        </span>
                    </div>
                    <div>
                        <span class="badge bg-primary-500">Django</span>
                        <span class="flex-auto">
                            <dt>Python Web Apps</dt>
                        </span>
                    </div>
                    <div>
                        <span class="badge bg-orange-700 mx-0">Rust</span>
                        <span class="flex-auto">
                            <dt>Fundamentals in Rust, Go</dt>
                        </span>
                    </div>
                    <!-- ... -->
                </dl>
            </section>
        </div>
        <div class="flex flex-col items-center card p-4 divide-y divide-dashed">
            <header class="card-header">
                <h3 class="h3">My Skills Include</h3>
            </header>
            <section class="flex flex-col items-center p-4 max-w-xs">
                <!-- ... -->
                <dl class="list-dl flex flex-col items-start">
                    <div>
                        <span class="badge bg-green-600">Programming</span>
                        <span class="flex-auto">
                            <dt>Python, C++, Bash</dt>
                        </span>
                    </div>
                    <div>
                        <span class="badge bg-blue-500">Technologies</span>
                        <span class="flex-auto">
                            <dt>Ubuntu, git, Docker, ROS</dt>
                        </span>
                    </div>
                    <div>
                        <span class="badge bg-slate-500">Tools</span>
                        <span class="flex-auto">
                            <dt>Vim, VSCode, GCC Compilers, SSH</dt>
                        </span>
                    </div>
                </dl>
            </section>
        </div>
        <div class="flex flex-col items-center card p-4 divide-y divide-dashed">
            <header class="card-header">
                <h3 class="h3">A Few Of My Hobbies Are</h3>
            </header>
            <section class="flex flex-col items-center p-4 max-w-xs">
                <!-- ... -->
                <dl class="list-dl flex flex-col items-">
                    <div>
                        <span class="badge bg-red-800">Motorcycle</span>
                        <span class="flex-auto">
                            <dt>Streaming Motorcycle Rides</dt>
                        </span>
                    </div>
                    <div>
                        <span class="badge bg-cyan-800">Climbing</span>
                        <span class="flex-auto">
                            <dt>Rock climbing (learning V4 routes)</dt>
                        </span>
                    </div>
                    <div>
                        <span class="badge bg-purple-700">Travelling</span>
                        <span class="flex-auto">
                            <dt>Planning to visit Germany</dt>
                        </span>
                    </div>
                </dl>
            </section>
        </div>
    </div>
</div>
<div class="flex flex-col justify-center items-center mx-auto my-48 md:my-80 p-4">
    <h1 class="h1 my-4 flex-auto">Contact Me</h1>
    <div class="card flex flex-col items-center justify-center p-4 text-center">
        <h4 class="h4">
            Send me an email at <a class="underline text-cyan-500" href="mailto:contact@matthewfritsch.com">contact@matthewfritsch.com</a>
        </h4>
        <h4 class="h4 inline">My current local time is <span class="underline inline text-orange-600 dark:text-green-300">{time}</span>.</h4>
        <h4 class="h4">I’ll return your email <span class="underline inline text-orange-600 dark:text-green-300">{response_time}</span></h4>
    </div>
</div>

