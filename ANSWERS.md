# Checkpoint answers

1. `onPress={handlePress}` passes a function for React Native to call when the user presses the component. `onPress={handlePress()}` calls it during rendering and passes its return value instead.

2. `Button` provides a simple native button with limited styling options. `Pressable` wraps custom content and gives more control over appearance and press feedback, so it is suitable for the profile actions and skill tags.

3. The style function receives an object containing the boolean `pressed` and returns styles. For example, `({ pressed }) => [styles.button, pressed && styles.pressed]` applies the feedback style while the component is pressed.

4. Assigning a state variable directly does not notify React to render again, and a variable declared with `const` cannot be reassigned. Use its setter, such as `setIsFollowing(previous => !previous)`, to request an update.

5. The follower count can be calculated entirely from `BASE_FOLLOWERS` and `isFollowing`, so a second state variable would duplicate information that could become inconsistent. A derived value is computed from existing data, here `BASE_FOLLOWERS + (isFollowing ? 1 : 0)`.

6. A controlled input displays the value held in React state and updates that state when the user types. The two props are `value={message}` and `onChangeText={setMessage}`.

7. `push` mutates the existing state array instead of creating a new one. To add a skill, use `setSelectedSkills(previous => [...previous, skill])`; to remove it, use `setSelectedSkills(previous => previous.filter(item => item !== skill))`.
