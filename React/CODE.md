# React Snippets

#### Hook Snippets

##### Before render hook

```typescript
const useBeforeFirstRender = (f: any): void => {
    const hasRendered = useRef(false);
    useEffect(() => {
        hasRendered.current = true;
    }, [hasRendered]);
    if (!hasRendered.current) {
        f();
    }
}

## Usage
useBeforeFirstRender(() => {
    // your code here
});

```

##### Calculate Window Dimensions

```typescript
function getWindowDimensions(): { windowWidth: number, windowHeight: number} {
  const { innerWidth: windowWidth, innerHeight: windowHeight } = window;
  return {
      windowWidth,
      windowHeight
  }
}

function UseWindowDimensions(): {
    windowWidth: number;
    windowHeight: number;
} {
    const [windowDimensions, setWindowDimensions] = useState(getWindowDimensions());

    useEffect(() => {
        function handleResize(): void {
            setWindowDimensions(getWindowDimensions());
        }

        window.addEventListener('resize', handleResize);

        return (): void => window.removeEventListener('resize', handleResize);
    }, []);

    return windowDimensions;
}

```

