# MTC VSCode Extension

A Visual Studio Code extension that provides code snippets for **MoveIt2** and **MoveIt Task Constructor (MTC)**, streamlining the development of complex robotic motion planning tasks.

## Overview

This extension accelerates development with MoveIt2 and MoveIt Task Constructor by providing ready-to-use code snippets for common patterns, stages, and task structures. Whether you're building pick-and-place operations, multi-stage manipulation tasks, or complex motion planning pipelines, these snippets help you write cleaner code faster.

## Features

- **MoveIt2 Snippets**: Quick access to common MoveIt2 patterns and configurations
- **MTC Stage Snippets**: Pre-configured snippets for all major MTC stage types
- **Task Structure Templates**: Complete task initialization and setup patterns
- **Planning Scene Management**: Snippets for scene configuration and object manipulation
- **Solver Configuration**: Quick templates for different planner types

## Installation

### From VS Code Marketplace

1. Open Visual Studio Code
2. Go to Extensions (Ctrl+Shift+X / Cmd+Shift+X)
3. Search for "moveit2" or "MoveIt Task Constructor"
4. Click Install

### From VSIX File

1. Download the `.vsix` file from the releases page
2. Open Visual Studio Code
3. Go to Extensions (Ctrl+Shift+X / Cmd+Shift+X)
4. Click the "..." menu at the top of the Extensions view
5. Select "Install from VSIX..."
6. Choose the downloaded `.vsix` file

## Usage

### Basic Usage

Type the snippet prefix in a C++ file and press `Tab` or `Enter` to expand the snippet. Snippets are designed to work in files where MoveIt2 and MTC are being used.

### Common Snippet Categories

#### Task Initialization

Create a complete MTC task structure:

```cpp
// Type: mtc-task-init
auto task = std::make_unique<moveit::task_constructor::Task>();
task->loadRobotModel(node);
```

#### Generator Stages

- **Current State**: Initialize with the robot's current state
- **Generate Grasp Pose**: Create grasp pose candidates
- **Generate Place Pose**: Create place pose candidates

#### Propagating Stages

- **Move To**: Move to a named pose or joint state
- **Move Relative**: Relative motion in Cartesian or joint space
- **Modify Planning Scene**: Attach/detach objects, modify collision rules

#### Connecting Stages

- **Connect**: Connect two planning stages with a motion plan
- **Merge**: Combine multiple solution branches

#### Container Stages

- **Serial Container**: Execute stages in sequence
- **Alternatives**: Try multiple strategies with fallbacks
- **Fallbacks**: Provide backup solutions
- **Parallel Container Merger**: Execute stages in parallel

### Example Workflow

1. **Start a new MTC task**:
   - Type `mtc-task-init` and expand
   - Configure your robot model and properties

2. **Add stages**:
   - Type `mtc-current-state` for the initial state
   - Type `mtc-moveto` to add movement stages
   - Type `mtc-connect` to connect planning segments

3. **Configure planners**:
   - Type `mtc-planner-pipeline` for sampling-based planning
   - Type `mtc-planner-cartesian` for Cartesian path planning
   - Type `mtc-planner-joint` for joint interpolation

4. **Execute the task**:
   - Use snippets for task planning and execution
   - Enable introspection for RViz visualization

## Snippet Reference

All snippets follow a consistent naming convention:

- `mtc-*`: MoveIt Task Constructor snippets
- `moveit-*`: General MoveIt2 snippets
- `mtc-stage-*`: Specific stage type snippets
- `mtc-container-*`: Container and wrapper snippets

### Key Snippets

| Prefix | Description |
|--------|-------------|
| `mtc-task-init` | Initialize a new MTC task |
| `mtc-current-state` | Add current state generator stage |
| `mtc-moveto` | Add MoveTo stage |
| `mtc-move-relative` | Add MoveRelative stage |
| `mtc-connect` | Add Connect stage |
| `mtc-serial-container` | Create a serial container |
| `mtc-alternatives` | Create alternatives container |
| `mtc-modify-scene` | Modify planning scene stage |
| `mtc-planner-pipeline` | Configure pipeline planner |
| `mtc-planner-cartesian` | Configure Cartesian planner |

## Requirements

- Visual Studio Code version 1.60.0 or higher
- C++ language support extension (recommended)
- MoveIt2 and MoveIt Task Constructor installed in your ROS 2 workspace

## Supported Languages

- C++ (`.cpp`, `.hpp`, `.h`, `.cc`)

## Configuration

The extension works out of the box with no additional configuration required. Snippets are automatically available in C++ files.

## About MoveIt Task Constructor

MoveIt Task Constructor (MTC) is a multi-stage planning framework for solving complex motion planning tasks in robotics. It allows developers to:

- Break down complex manipulation tasks into simpler, reusable stages
- Compose hierarchical task structures with sequential or parallel execution
- Visualize and debug individual stage solutions
- Optimize for total cost across all stages

### Key Concepts

- **Generators**: Create solutions independently (e.g., current state, grasp poses)
- **Propagators**: Receive input from one neighbor, solve, and pass to the other side
- **Connectors**: Connect start and goal states provided by adjacent stages
- **Containers**: Group multiple stages with different execution patterns

## Contributing

Contributions are welcome! If you have suggestions for new snippets or improvements:

1. Fork the repository
2. Create a feature branch
3. Add your snippets following the existing format
4. Submit a pull request with a clear description

## Resources

- [MoveIt2 Documentation](https://moveit.picknik.ai/)
- [MoveIt Task Constructor Documentation](https://moveit.github.io/moveit_task_constructor/)
- [MoveIt Task Constructor Tutorial](https://moveit.picknik.ai/main/doc/tutorials/pick_and_place_with_moveit_task_constructor/pick_and_place_with_moveit_task_constructor.html)
- [MoveIt Task Constructor GitHub](https://github.com/moveit/moveit_task_constructor)

## License

This extension is provided as-is for the robotics development community.

## Feedback and Issues

If you encounter any issues or have suggestions for improvements:

- Report issues on the [GitHub repository](https://github.com/logesh1516/MTC_vscode_extension)
- Request new snippets or features
- Share your experience using the extension

## Changelog

### Version 0.0.1 (Initial Release)

- Initial release with core MTC and MoveIt2 snippets
- Support for all major MTC stage types
- Task initialization and configuration snippets
- Planner configuration templates
- Planning scene management snippets

---

**Happy Robot Programming!** 🤖

Made with ❤️ for the ROS 2 and MoveIt2 community
