pipeline {
agent any
environment {
DOCKER = &#39;&quot;C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe&quot;&#39;
}
stages {
stage(&#39;Build Docker Image&#39;) {
steps {
bat &#39;%DOCKER% build -t python-app .&#39;
}
}

stage(&#39;Run Tests Inside Docker&#39;) {
steps {
bat &#39;%DOCKER% run --rm python-app pytest&#39;
}
}
stage(&#39;Run Application&#39;) {
steps {
bat &#39;%DOCKER% run --rm python-app&#39;
}
}
}
}