---
title: Smooth 2D Camera Follow In Unity3D
date:  2016-12-28 17:56:06 +0100
tags: Unity
author: Salus Games
toc: true
---

This is just a nice short and simple script that I sometimes use to make the camera in Unity smoothly follow an object. Just add this script to a orthographic camera and select a target and follow speed in the inspector.

### The Code

{% highlight c# %}
using UnityEngine;

public class CameraFollow2D : MonoBehaviour
{
    public float FollowSpeed = 2f;
    public Transform Target;

    private void Update()
    {
        Vector3 newPosition = Target.position;
        newPosition.z = -10;
        transform.position = Vector3.Slerp(transform.position, newPosition, FollowSpeed * Time.deltaTime);
    }
}
{% endhighlight %}
