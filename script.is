
let tasks = [];
let completedCount = 0;

function addTask() {
    const subject = document.getElementById("subject").value.trim();
    const taskName = document.getElementById("task").value.trim();
    const hours = document.getElementById("hours").value;

    if (!subject || !taskName || !hours) {
        alert("Please fill in all fields.");
        return;
    }

    tasks.push({
        subject: subject,
        name: taskName,
        hours: Number(hours),
        completed: false
    });

    document.getElementById("subject").value = "";
    document.getElementById("task").value = "";
    document.getElementById("hours").value = "";

    displayTasks();
}

function displayTasks() {
    const list = document.getElementById("taskList");

    if (tasks.length === 0) {
        list.innerHTML = '<p class="empty">No tasks added yet.</p>';
        updateStats();
        return;
    }

    list.innerHTML = "";

    tasks.forEach((item, index) => {
        const task = document.createElement("div");
        task.className = "task";

        task.innerHTML = `
            <div class="${item.completed ? "completed" : ""}">
                <h3>${item.subject}</h3>
                <p>${item.name} • ${item.hours} hour(s)</p>
            </div>

            <button onclick="completeTask(${index})">
                ${item.completed ? "Completed" : "Mark Done"}
            </button>
        `;

        list.appendChild(task);
    });

    updateStats();
}

function completeTask(index) {
    if (!tasks[index].completed) {
        tasks[index].completed = true;
        completedCount++;
    }

    displayTasks();
}

function updateStats() {
    const totalHours = tasks.reduce((sum, task) => sum + task.hours, 0);

    document.getElementById("total").textContent = tasks.length;
    document.getElementById("completed").textContent = completedCount;
    document.getElementById("hoursTotal").textContent = totalHours;
}