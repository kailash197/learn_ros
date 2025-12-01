ROS Rolling is one of the official **ROS 2 distributions**, but it’s a special one:

*   **Rolling Release**: Unlike stable distributions (like Humble or Iron), Rolling is a *development distribution*. It’s continuously updated with the latest features, bug fixes, and experimental changes.
*   **Purpose**: It serves as a preview of what will become the next stable ROS 2 release. Developers use it to test new functionality and prepare for future versions.
*   **Stability**: It’s not recommended for production systems because APIs and packages can change frequently. However, it’s great for cutting-edge development.
*   **Support**: Rolling doesn’t have a fixed end-of-life date because it’s always evolving. When a new stable release comes out, Rolling moves forward toward the next one.

Think of it as the **“bleeding edge”** version of ROS 2.

***

### ✅ **When You SHOULD Use ROS Rolling**

1.  **Cutting-Edge Development**
    *   If you want to experiment with the latest ROS 2 features before they appear in stable releases.
    *   Ideal for contributing to ROS 2 core or testing new packages.

2.  **Package Development**
    *   If you maintain or develop ROS 2 packages and need to ensure compatibility with future releases.

3.  **Research & Prototyping**
    *   For academic or experimental projects where stability is less critical and new features matter.

***

### ❌ **When You SHOULD NOT Use ROS Rolling**

1.  **Production Systems**
    *   Rolling is not stable; APIs and packages can change without warning.
    *   Avoid using it for robots deployed in real-world environments.

2.  **Long-Term Projects**
    *   If your project needs guaranteed stability and long-term support, use an LTS release like **Humble** or **Iron**.

3.  **Beginner Learning**
    *   If you’re new to ROS, Rolling can be confusing because tutorials and packages may break due to frequent updates.

***

**Rule of Thumb:**

*   **Rolling = bleeding edge, unstable, for developers and testers.**
*   **Stable releases (Humble, Iron) = reliable, for production and learning.**

***
