stage('Run Selenium Test') {
    steps {
        sh '''
        # Kill any existing Xvfb on :99 (ignore errors if none running)
        sudo pkill Xvfb || true

        # Remove stale lock file (if exists)
        sudo rm -f /tmp/.X99-lock || true

        # Start virtual display
        Xvfb :99 -screen 0 1024x768x16 &
        export DISPLAY=:99

        # Wait a few seconds for Xvfb to start
        sleep 3

        # Activate virtual environment and run Selenium test
        . venv/bin/activate
        python test.py
        '''
    }
}
