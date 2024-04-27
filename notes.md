schema:animstategraph:getDefaultData
assets:create:animstategraph
picker:animstategraph
animstategraph:editor:open


var ANIM_SCHEMA = {
    NODE: {
        STATE: 0,
        DEFAULT_STATE: 1,
        START_STATE: 3,
        ANY_STATE: 4,
        END_STATE: 5
    },
    EDGE: {
        TRANSITION_DEFAULT: 0,
        TRANSITION: 1,
        TRANSITION_FROM_ANY: 3
    }
};

var visualScriptingContext = [
    {
        text: 'Add new node',
        action: 'add_new_scripting_node',
        nodeType: ANIM_SCHEMA.NODE.STATE,
        attributes: {
            name: 'New state'
        }
    }
];

var initialData = {
    nodes: {
        [ANIM_SCHEMA.NODE.ANY_STATE]: {
            name: 'state',
            fill: 'rgb(54, 67, 70, 0.8)',
            stroke: '#20292b',
            icon: '',
            iconColor: '#FFFFFF',
            nodeType: ANIM_SCHEMA.NODE.ANY_STATE,
            posX: 100,
            posY: 100,
            attributes: [
                {
                    name: 'condition',
                    type: 'TEXT_INPUT'
                },
                {
                    name: 'key',
                    type: 'TEXT_INPUT'
                },
                {
                    name: 'state',
                    type: 'VEC_3_INPUT',
                    defaultValue: [0, 0, 0]
                }
            ]
        }
    },
    edges : {}
}

var graph = new pcuiGraph.Graph(initialData, {
    dom: editor.call('layout.assets').dom,
    initialData: initialData,
    contextMenuItems: visualScriptingContext,
    readOnly: false,
    includeFonts: false,
    incrementNodeNames: true,
    passiveUIEvents: true,
    useGlobalPCUI: true,
    adjustVertices: true,
    defaultStyles: {
        background: {
            gridSize: 10
        }
    }
});







