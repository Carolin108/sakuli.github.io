---
title: Screenshot based Testing
---

A lot of end-to-end scenarios exceed the borders of your browser and the capabilities of webdriver. This might include common use cases like a drag and drop from the host system to a webpage or exporting a report into a spreadsheet or pdf-format. In these cases, your webbased tests can be extended to also validate behavior and invoke interactions outside the browser, all within a single test.

Of course, you can also use Sakuli’s native testing power on its own, e.g. rich-client testing of SAP, Office or proprietary software systems. Sakuli accomplishes its native capabilities by scanning the whole screen (or a dedicated region) on a stand-alone computer or in headless container screens, searching for provided image patterns.

Screenshot based actions are relying on an abstract `Region` class, which represents an abstract region on the desktop.
When creating a new instance without parameters, a `Region` spans the whole desktop.
But it is also possible to create new regions by specifying `left`, `top`, `width` and `height` parameters.

The following example showcases a test which drags a source element to a target region.
In this demo scenario, both source and target are located on screen via template image.

{{< highlight typescript "linenos=table" >}}
(async () => {
    const testCase = new TestCase("native_keyboard_demo");
    const url = "https://codepen.io/akifo/pen/LGraWZ";
    const screen = new Region();
    try {
        await _navigateTo(url);
        await screen.find("drag.png").mouseMove().dragAndDropTo(await screen.find("target.png"));
    } catch (e) {
        await testCase.handleException(e);
    } finally {
        testCase.saveResult();
    }
})().then(done);
{{< /highlight >}}

The `dragAndDropTo(...)` methods always moves straight to the target region.
In order to follow a more complex path, it is also possible to perform the drag gesture manually.
Once the source image has been located on screen, Sakuli moves the mouse to its location and presses and holds the left mouse button.
Afterwards, it locates the target image, moves the mouse there while still holding the mouse button and releases it, once it reaches the target location.

{{< highlight typescript "linenos=table" >}}
(async () => {
    const testCase = new TestCase("native_demo");
    const url = "https://codepen.io/akifo/pen/LGraWZ";
    const screen = new Region();
    try {
        await _navigateTo(url);
        await screen.find("source.png").mouseMove().mouseDown(MouseButton.LEFT);
        await new Region(0, 0, 10, 10).mouseMove();
        await new Region(500, 300, 50, 100).mouseMove();
        await screen.find("target.png").mouseMove().mouseUp(MouseButton.LEFT);
    } catch (e) {
        await testCase.handleException(e);
    } finally {
        testCase.saveResult();
    }
})().then(done);
{{< /highlight >}}
