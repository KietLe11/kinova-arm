# Define phony targets to ensure 'make' runs the commands and not a file named 'build' or 'source'
.PHONY: build source all clean

# ---------------------------------------------------------------------------------
# DEFAULT TARGET
# Runs the full build, then sources the environment (what you had originally)
# ---------------------------------------------------------------------------------
all: build

# ---------------------------------------------------------------------------------
# 1. build: Compiles the workspace and sources the local environment
# ---------------------------------------------------------------------------------
build:
	# Source the ROS distribution (e.g., Humble)
	source /opt/ros/humble/setup.bash && \
	# Build the workspace
	colcon build && \
	# Source the local workspace setup file
	source install/setup.bash

# ---------------------------------------------------------------------------------
# 2. source: Sources the environment *without* building
# ---------------------------------------------------------------------------------
source:
	# Note: This is meant to be copied/pasted into the terminal,
	# as 'make' executes commands in a *sub-shell* which doesn't
	# persist environment changes.
	@echo "========================================================"
	@echo "To source your environment, COPY AND PASTE the line below:"
	@echo "source /opt/ros/humble/setup.bash && source install/setup.bash"
	@echo "========================================================"
	@echo " "

# ---------------------------------------------------------------------------------
# 3. clean: Optional but highly recommended
# ---------------------------------------------------------------------------------
clean:
	rm -rf build install log
	@echo "Workspace cleaned (build, install, and log directories removed)."